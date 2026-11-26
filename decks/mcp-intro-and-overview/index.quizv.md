---
title: MCP intro and overview
description: >
  Intro to MCP for developers
theme: default
author: Maxime Lenne — White Wood Tech
tags: [mcp, ai, llm, integration]
max-questions: 10
target-difficulty: medium
---

---
type: single
timer: 18
difficulty: easy
tags: [genai, transformer, history]
---

## En quelle année et sous quel titre a été publié l'article fondateur de l'architecture Transformer ?

- [ ] 2012 — « ImageNet Classification with Deep CNNs »
- [x] 2017 — « Attention is All You Need »
- [ ] 2020 — « Language Models are Few-Shot Learners »
- [ ] 2022 — « Training language models with human feedback »

> En **2017**, une équipe de Google publie **« Attention is All You Need »**, un article de 8 pages qui
> introduit le **Transformer** — l'architecture aujourd'hui à la base de tous les LLM modernes (Claude,
> GPT, Gemini, Mistral, Llama). Les autres articles cités sont importants mais postérieurs et bâtis sur
> cette fondation.

---
type: multiple
timer: 25
difficulty: medium
tags: [genai]
---

## Quelles sont les trois grandes familles de modèles d'IA générative ?

- [x] Les GAN (réseaux adversariaux)
- [x] Les modèles de diffusion
- [x] Les LLM (Large Language Models)
- [ ] Le Reinforcement Learning

> Les trois familles de l'IA générative sont les **GAN** (deux réseaux en compétition, ex. deepfakes,
> StyleGAN), les **modèles de diffusion** (partent du bruit, ex. Stable Diffusion, Midjourney) et les
> **LLM** (prédisent le prochain token, ex. Claude, GPT). Les RNN et CNN sont des architectures plus
> anciennes ou spécialisées ; le Reinforcement Learning est une approche d'entraînement, pas une famille
> générative.

---
type: multiple
timer: 25
difficulty: medium
tags: [llm-limits]
---

## Parmi les affirmations suivantes, lesquelles décrivent des limites réelles des LLM ?

- [x] Ils peuvent halluciner — inventer des faits avec confiance
- [x] Ils ont une date de coupure des données d'entraînement
- [x] Leur fenêtre de contexte est limitée
- [ ] Ils accèdent en permanence à Internet en temps réel

> Les LLM **hallucinent** (inventent des faits), ont une **date de coupure** (ils ignorent les événements
> postérieurs à leur entraînement), une **fenêtre de contexte limitée** (ils ne voient que le contexte
> courant) et sont **faibles en calcul** car ils prédisent des tokens numériques sans calculer. Un LLM
> seul **n'a pas d'accès Internet** — il faut le brancher à un outil — et la qualité linguistique varie
> fortement entre les langues.

---
type: single
timer: 22
difficulty: medium
tags: [genai, llm-limits]
---

## Que contrôle le paramètre « température » d'un LLM ?

- [ ] La vitesse de génération des tokens
- [x] Le caractère déterministe ou créatif des réponses
- [ ] La taille maximale de la fenêtre de contexte
- [ ] Le coût en tokens d'une requête

> La **température** contrôle le caractère probabiliste des réponses. À **`temperature=0`**, le modèle
> est déterministe et reproductible (utile pour extraction ou classification). À **`temperature=1`**,
> les réponses sont plus variées et créatives (utile pour brainstorming ou rédaction). La vitesse, le
> contexte et le coût sont des paramètres techniques indépendants.

---
type: single
timer: 18
difficulty: easy
tags: [llm-limits, rag]
---

## Quelle image résume le mieux la limitation fondamentale d'un LLM seul, sans outils ni données externes ?

- [x] Un expert brillant enfermé dans une pièce sans fenêtre
- [ ] Une calculatrice surpuissante mais coûteuse
- [ ] Une base de données vivante qui se met à jour seule
- [ ] Un moteur de recherche en temps réel

> Un **LLM seul** est comme **« un expert brillant enfermé dans une pièce sans fenêtre »** : son savoir
> est figé à sa date de coupure, il ne voit pas vos documents internes et ne peut rien faire dans le
> monde réel. C'est précisément cette limite que **RAG, les agents et MCP** viennent adresser — en
> ouvrant des « portes » vers les données et les actions.

---
type: single
timer: 18
difficulty: easy
tags: [mcp-why]
---

## Quel problème central MCP cherche-t-il à résoudre ?

- [ ] Le coût élevé des tokens des LLM
- [x] Les intégrations N×M entre apps IA et services
- [ ] Le manque de modèles open source performants
- [ ] La latence des APIs LLM

> Avant MCP, chaque app IA (Claude, Cursor, agents…) devait écrire ses propres intégrations pour chaque
> service (GitHub, Sentry, DB…), soit **N × M intégrations custom** à maintenir. MCP standardise ce
> contrat : N apps + M servers parlent **un seul protocole**, ce qui ramène le problème à **N + M**.
> Le coût des tokens, l'open source et la latence sont d'autres sujets, non adressés par MCP.

---
type: single
timer: 22
difficulty: medium
tags: [mcp-why]
---

## Comment qualifier le mieux MCP d'un point de vue technique ?

- [ ] Une API REST standardisée pour les LLM
- [ ] Un format de fichier de configuration
- [x] Un protocole stateful avec lifecycle et capabilities
- [ ] Une bibliothèque Python d'inférence LLM

> MCP **n'est pas une API** au sens REST. C'est un **protocole stateful** (basé sur **JSON-RPC 2.0**)
> avec son **lifecycle** (`initialize`, `shutdown`), sa **négociation de capabilities** à l'init, et des
> primitives strictes (tools, resources, prompts). Conceptuellement, il est plus proche de **LSP**
> (Language Server Protocol) que d'une API REST.

---
type: single
timer: 20
difficulty: medium
tags: [mcp-why, usb-c]
---

## Quelle analogie est couramment utilisée pour expliquer MCP au grand public ?

- [x] « L'USB-C de l'IA »
- [ ] « Le HTML des LLM »
- [ ] « Le Wi-Fi des agents »
- [ ] « Le Docker des modèles »

> MCP est souvent appelé **« l'USB-C de l'IA »** : avant l'USB-C, chaque appareil avait son propre câble ;
> avec l'USB-C, un seul câble universel. De la même manière, MCP fournit **un seul protocole** pour
> brancher n'importe quel outil (GitHub, Figma, Supabase…) à n'importe quel agent compatible (Claude
> Code, Cursor…).

---
type: single
timer: 28
difficulty: hard
tags: [mcp-why, architecture]
---

## Avec **N** apps IA et **M** services à connecter, combien d'intégrations faut-il maintenir avec MCP ?

- [ ] N × M
- [x] N + M
- [ ] N²
- [ ] 2 × (N + M)

> Avec MCP, chaque app implémente **une seule fois** le protocole côté client, et chaque service **une
> seule fois** côté server : on passe de **N × M** intégrations custom à **N + M** implémentations
> indépendantes, branchables entre elles. C'est l'argument principal qui justifie l'existence d'un
> protocole standard plutôt que d'APIs propriétaires.

---
type: single
timer: 18
difficulty: easy
tags: [architecture]
---

## Quels sont les trois composants principaux d'une architecture MCP ?

- [ ] Frontend, Backend, Base de données
- [ ] Proxy, Gateway, Worker
- [x] Host, Client, Server
- [ ] Producer, Broker, Consumer

> L'architecture MCP repose sur trois rôles : le **Host** (l'application IA visible, ex. Claude Desktop,
> VS Code), le **Client** (composant logique interne qui porte une connexion vers un server) et le
> **Server** (programme indépendant qui expose tools/resources/prompts). Les autres triplets décrivent
> des architectures web, réseau ou messaging.

---
type: single
timer: 22
difficulty: medium
tags: [architecture, client]
---

## Quelle affirmation décrit correctement la relation entre Host, Client et Server dans MCP ?

- [ ] 1 Host = 1 Client = 1 Server (relation 1:1:1 globale)
- [ ] 1 Client peut parler à plusieurs Servers via une seule connexion
- [x] 1 Host → N clients, et 1 client ↔ 1 server ↔ 1 connexion
- [ ] 1 Server ne peut être consommé que par 1 seul Host à la fois

> Un **Host** instancie **plusieurs clients**, mais **chaque client porte une connexion dédiée vers un
> seul server** (relation **1:1:1 par connexion**). C'est le Host qui consolide les capacités exposées
> par tous les servers pour le modèle. Un même server remote (HTTP) peut par ailleurs servir plusieurs
> hosts simultanément.

---
type: multiple
timer: 25
difficulty: medium
tags: [architecture, host]
---

## Quelles responsabilités sont assurées par le Host dans une architecture MCP ?

- [x] Instancier et gérer les clients
- [x] Appliquer les politiques (auth, permissions, sampling)
- [x] Consolider les capacités de tous les servers pour le modèle
- [ ] Exécuter directement le code des tools à la place du server

> Le **Host** est la couche de coordination : il **instancie les clients**, **applique les politiques**
> (auth, permissions, sampling) et **agrège les capabilities** des différents servers pour les rendre
> disponibles au modèle. Il **n'exécute pas les tools** — c'est le server qui les exécute — et **ne
> stocke pas d'embeddings** (cela relève d'une base vectorielle dans un pipeline RAG).

---
type: single
timer: 25
difficulty: medium
tags: [transport, stdio, http]
---

## Quelle est la différence principale entre le transport stdio et le transport HTTP (streamable) en MCP ?

- [x] stdio est local et mono-client ; HTTP est remote et multi-client
- [ ] stdio est multi-client ; HTTP est mono-client
- [ ] stdio nécessite OAuth ; HTTP n'a pas besoin d'auth
- [ ] stdio est plus lent que HTTP car il passe par le réseau

> Le transport **stdio** lance le server comme un **process local** (stdin/stdout) — il est
> **mono-client** et offre la perf maximale, sans réseau ni auth. Le transport **Streamable HTTP**
> expose un server **remote** (HTTP POST + SSE optionnel) accessible à **plusieurs hosts**
> simultanément, ce qui justifie l'usage recommandé d'**OAuth 2.1**. stdio ne passe pas par le réseau,
> donc il n'est jamais plus lent que HTTP.

---
type: multiple
timer: 30
difficulty: hard
tags: [data-layer, json-rpc, primitives]
---

## Parmi les éléments suivants, lesquels appartiennent au **data layer** de MCP (par opposition au transport layer) ?

- [x] Le protocole JSON-RPC 2.0
- [x] Le lifecycle (initialize, shutdown)
- [x] Les primitives tools / resources / prompts
- [ ] Le framing HTTP / Server-Sent Events

> Le **data layer** est l'« oignon intérieur » du protocole : **JSON-RPC 2.0**, **lifecycle**,
> **capabilities negotiation**, **primitives** et notifications temps réel — **identique quel que soit
> le transport**. Le **transport layer** est l'extérieur swappable : **stdio** (stdin/stdout),
> **Streamable HTTP** (framing HTTP, SSE) et l'**authentification** (OAuth, bearer, API keys). Cette
> séparation est ce qui rend MCP futur-proof.

---
type: single
timer: 22
difficulty: medium
tags: [transport, http]
---

## Quel mécanisme d'authentification est recommandé pour un serveur MCP **remote** (transport HTTP) ?

- [ ] HTTP Basic Auth
- [ ] API Key dans l'URL
- [x] OAuth 2.1
- [ ] SAML 2.0

> Pour un server MCP **remote** accessible par plusieurs hosts via HTTP, **OAuth 2.1** est l'auth
> recommandée — elle gère l'autorisation déléguée, le refresh de tokens et s'aligne sur les pratiques
> modernes du web. Un server **local** (stdio) ne nécessite pas d'auth puisqu'il tourne déjà sur la
> machine de l'utilisateur. Basic Auth, API keys en URL et SAML sont soit insécures, soit inadaptés
> à ce cas.

---
type: single
timer: 20
difficulty: medium
tags: [rag]
---

## Que signifie l'acronyme RAG ?

- [ ] Random Access Generation
- [x] Retrieval-Augmented Generation
- [ ] Recursive Agent Graph
- [ ] Retrieval And Grading

> **RAG** signifie **Retrieval-Augmented Generation** : on **récupère** (Retrieve) les documents
> pertinents, on **augmente** le prompt avec ces documents, puis le LLM **génère** une réponse informée
> et sourcée. C'est la technique la plus utilisée en production pour les chatbots d'entreprise qui
> doivent répondre sur une base documentaire interne.

---
type: single
timer: 22
difficulty: medium
tags: [agents]
---

## Quelle est la différence fondamentale entre un chatbot et un agent IA ?

- [ ] Un agent répond plus rapidement qu'un chatbot
- [ ] Un chatbot consomme plus de tokens qu'un agent
- [x] Un agent planifie et exécute des actions en boucle pour accomplir une tâche
- [ ] La différence est purement d'interface utilisateur

> Un **chatbot** est réactif : il répond à une question, donne une information, mais ne prend pas
> d'initiative. Un **agent IA** est autonome et orienté tâche : il **planifie** les étapes, **exécute**
> des actions (appels API, code, recherche), **observe** les résultats et **boucle** jusqu'à atteindre
> l'objectif. La formule à retenir : **Agent = LLM + Outils + Boucle d'exécution**.

---
type: single
timer: 22
difficulty: medium
tags: [agents]
---

## Que signifient les trois étapes de la boucle **ReAct** utilisée par les agents IA ?

- [x] Reason — Act — Observe
- [ ] Read — Execute — Acknowledge
- [ ] Request — Authenticate — Continue
- [ ] Retrieve — Augment — Classify

> La boucle **ReAct** (Reasoning + Acting) enchaîne : **Reason** (le LLM raisonne sur quoi faire),
> **Act** (il exécute un outil), **Observe** (il analyse le résultat) — puis recommence jusqu'à
> atteindre l'objectif. C'est ce pattern qui sous-tend Claude Code, Cursor et la plupart des agents
> modernes.

---
type: single
timer: 28
difficulty: hard
tags: [history]
---

## Quand Anthropic a-t-il lancé MCP en open source ?

- [ ] Octobre 2023
- [ ] Juin 2024
- [x] Novembre 2024
- [ ] Janvier 2025

> Anthropic a publié **MCP en open source en novembre 2024**. **OpenAI l'a adopté en mars 2025**, faisant
> de MCP le standard de facto pour connecter les agents IA à des outils externes — un signe que
> l'écosystème converge rapidement autour d'un protocole commun.

---
type: multiple
timer: 28
difficulty: hard
tags: [primitives, architecture]
---

## Quelles sont les **trois primitives** qu'un serveur MCP peut exposer ?

- [x] Tools (actions exécutables)
- [x] Resources (données accessibles)
- [x] Prompts (templates réutilisables)
- [ ] Sampling

> Côté **server**, MCP définit trois primitives : **tools** (actions exécutables, ex. créer un fichier,
> requête SQL), **resources** (données accessibles, ex. doc, schéma DB) et **prompts** (templates de
> workflows réutilisables). Les distracteurs — **sampling**, **elicitation**, **roots** — sont des
> primitives côté **client** (le host les expose au server, pas l'inverse). Bien distinguer les deux
> est essentiel pour concevoir un MCP.
