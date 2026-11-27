# HashQuiz demo decks

A step-by-step example of how to use [HashQuiz](https://github.com/WhiteWoodTech/hashquiz): write a
quiz in Markdown, play it live with an audience, and publish it on the web with
[Vercel](https://vercel.com) and [Supabase](https://supabase.com).

HashQuiz is a real-time multiplayer quiz, a Kahoot alternative. The host shows the questions on a
big screen and the players answer from their phones. Everything comes from the
[`hashquiz`](https://www.npmjs.com/package/hashquiz) npm package, so this repository only holds a
deck and three small config files. Fork it to start your own.

## What's in this repository

```text
decks/
  genai-introduction/
    index.hashquiz.md  # the quiz: 10 questions on generative AI
  genai-introduction-solo/
    index.hashquiz.md  # the same quiz with `solo: true`, to play alone
package.json           # the hashquiz CLI and three scripts: check, dev, build
vercel.json            # how Vercel builds and serves the site
.env.example           # the Supabase settings used by the build
.github/workflows/
  ci.yml               # checks and builds the decks on every push
```

Once it's deployed, the site has two pages:

| URL | Who uses it | What it does |
| --- | --- | --- |
| `/host` | The presenter | Picks a deck, opens a room, shows the questions and the podium |
| `/` | The players | Join the room with its code (or a QR code) and answer |

## Step 1. Install

You need [Bun](https://bun.sh) 1.1 or later.

```bash
git clone https://github.com/maxime-lenne/hashquiz-decks.git
cd hashquiz-decks
bun install
```

`bun install` installs the `hashquiz` CLI. To start from an empty folder instead, run
`bun init` and then `bun add -d hashquiz@beta`, and copy `vercel.json` and the scripts of
`package.json`.

## Step 2. Write a deck

A deck is one Markdown file with the `.hashquiz.md` extension, `decks/<slug>/index.hashquiz.md`. It starts with a frontmatter that
describes the quiz:

```markdown
---
title: Introduction à l'IA Générative
description: >
  Deck de démonstration HashQuiz : 10 questions sur les bases
  de l'IA générative, des LLM, du prompt et du RAG.
theme: default
author: Maxime Lenne
tags: [ia, llm, prompt, rag, gen-ai]
---
```

Each question has its own small frontmatter, then the question, its choices and an explanation:

```markdown
---
type: single
timer: 20
difficulty: easy
tags: [ia, histoire]
---

## En quelle année a été publié l'article "Attention is All You Need" qui a révolutionné l'IA ?

- [ ] 2012
- [ ] 2015
- [x] 2017
- [ ] 2022

> L'article **"Attention is All You Need"** de Vaswani et al. (Google, 2017) a introduit l'architecture
> **Transformer**, qui est aujourd'hui la base de tous les LLM modernes.
```

| Part | Meaning |
| --- | --- |
| `type` | `single` (one right answer) or `multiple` (several, say "sélectionnez 3" in the question) |
| `timer` | Seconds to answer, 20 by default. A faster answer scores more points (500 to 1,000) |
| `difficulty` | `easy`, `medium` or `hard` |
| `## ...` | The question |
| `- [x]` / `- [ ]` | A right / wrong choice. Always write **exactly 4 choices** that look alike |
| `> ...` | The explanation shown after the answer is revealed |

Open [`decks/genai-introduction/index.hashquiz.md`](decks/genai-introduction/index.hashquiz.md) for the
full example, including a `multiple` question. To add a deck, create another folder in `decks/`.

## Step 3. Check and play locally

```bash
bun run check                                           # validate every deck
bun run dev decks/genai-introduction/index.hashquiz.md  # start a local game
```

`bun run dev` needs no account. It starts the host on <http://localhost:3031/host/> and the
players on <http://localhost:3032>. Open the host and pick the deck: a lobby opens with a room code
and a QR code. Join it from one or two other tabs, then click **Start Game** on the host.

## Step 4. Create the Supabase project

Online, the host and the players are on different devices. HashQuiz sends the game messages through
[Supabase Realtime](https://supabase.com/docs/guides/realtime), so you need a Supabase project.
The free plan is enough, and a multiplayer game needs no table or schema.

1. On <https://supabase.com>, create a new project.
2. In **Project Settings → API**, copy the **Project URL** and the **anon public** key.

The anon key is meant to be public: it ends up in the site's `hashquiz-config.js`.

## Step 5. Build the site

`bun run build` turns every deck in `decks/` into a static site in `dist/`:

```text
dist/
  index.html          # player app
  host/index.html     # host app
  host/decks.json     # the deck list read by the host
  hashquiz-config.js  # the settings below, read by both apps at runtime
```

The build reads its settings from the environment. To try a Supabase build locally, copy
`.env.example` to `.env` and fill in the values from step 4 (Bun loads `.env` by itself):

| Variable | Value |
| --- | --- |
| `HASHQUIZ_TRANSPORT` | `supabase` (without it, the site only works with `bun run dev`) |
| `HASHQUIZ_SUPABASE_URL` | The Project URL |
| `HASHQUIZ_SUPABASE_ANON_KEY` | The anon public key |

## Step 6. Deploy on Vercel

1. Push your repository to GitHub.
2. On <https://vercel.com/new>, import it. Leave the framework preset on **Other**.
3. In **Environment Variables**, add the three variables of step 5 for Production and Preview.
4. Click **Deploy**.

You don't need to set the build command or the output folder: [`vercel.json`](vercel.json) does it.

```json
{
  "buildCommand": "bun run build",
  "outputDirectory": "dist",
  "framework": null,
  "rewrites": [
    { "source": "/host", "destination": "/host/index.html" },
    { "source": "/host/(.*)", "destination": "/host/$1" },
    { "source": "/((?!host/|host$).*)", "destination": "/$1" }
  ]
}
```

The rewrites send `/host` to the host app and every other path to the player app. From now on,
each push redeploys the site.

## Step 7. Play online

1. Open `https://<your-domain>/host` on the big screen and pick the deck.
2. Players scan the QR code of the lobby, or open `https://<your-domain>/` and type the room code.
3. Click **Start Game**. After the last question, the host shows the podium.

## Going further

- **Solo mode**: a deck with `solo: true` can also be played alone, with a leaderboard, like
  [`genai-introduction-solo`](decks/genai-introduction-solo/index.hashquiz.md). The player home lists it
  under the join form, and its host card shows **Jouer en solo**. Locally,
  `bun run dev decks` (the folder, not a single file) serves it with no setup and keeps the runs in `.hashquiz/solo.db`. Online, it needs the
  HashQuiz schema in Supabase, which one command deploys once the site is live (it needs the
  [Supabase CLI](https://supabase.com/docs/guides/cli), and `SUPABASE_ACCESS_TOKEN` and
  `SUPABASE_DB_PASSWORD` in the environment):

  ```bash
  HASHQUIZ_SITE_URL=https://<your-domain> bunx hashquiz supabase deploy --project <project-ref>
  ```

- **Every option** of the CLI and the build: the
  [`hashquiz` package docs](https://github.com/WhiteWoodTech/hashquiz/blob/develop/docs/PACKAGE.md).

## License

[MIT](LICENSE)
