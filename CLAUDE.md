# CLAUDE.md

This repository is a public demo of a HashQuiz decks repository. Keep it small and didactic:
the README is a step-by-step tutorial, so update it with any change.

```bash
bun install                                            # install the hashquiz CLI
bun run check                                          # validate every deck
bun run dev decks/genai-introduction/index.hashquiz.md # local game
bun run build                                          # static site in dist/ (Vercel)
```

- Decks only: the quiz engine is the `hashquiz` npm package (source: WhiteWoodTech/hashquiz). Never copy its code here.
- One folder per deck, `decks/<slug>/index.hashquiz.md`. Every question has exactly 4 choices. `.quizv.md` files are not read.
