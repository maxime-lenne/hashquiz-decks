---
title: AI Dev Quiz
description: >
  Quiz sur l'IA et le développement IA — LLM, Prompt Engineering,
  Context Engineering, Agents, Agentic Coding, RAG
theme: default
author: HashQuiz
tags: [ia, llm, prompt, agents, rag, coding]
one-shoot: true
max-questions: 12
target-difficulty: hard
---

---
type: single
timer: 20
difficulty: easy
tags: [ia, llm]
---

## Que signifie l'acronyme LLM ?

- [x] Large Language Model
- [ ] Logical Learning Machine
- [ ] Linear Language Module
- [ ] Low Latency Mechanism

> LLM = **Large Language Model**. Un modèle de langage entraîné sur de vastes corpus pour prédire et générer du texte en
> se basant sur des probabilités sur les tokens suivants.

---
type: single
timer: 20
difficulty: medium
tags: [ia, llm]
---

## Quelle architecture est à la base de la quasi-totalité des LLM modernes (GPT, Claude, Gemini) ?

- [ ] CNN (Convolutional Neural Network)
- [ ] RNN (Recurrent Neural Network)
- [x] Transformer (self-attention)
- [ ] GAN (Generative Adversarial Network)

> L'architecture **Transformer** (Vaswani et al., 2017 — "Attention is All You Need") est le socle de tous les LLM
> modernes. Le mécanisme de self-attention permet de capturer les dépendances entre tokens sur l'ensemble de la
> séquence.

---
type: single
timer: 20
difficulty: medium
tags: [ia, llm]
---

## Quelle est la différence clé entre un modèle de type GPT-4 et un modèle "reasoning" de type o1/o3 ?

- [ ] o1 génère uniquement du code
- [x] o1 utilise une chaîne de réflexion interne
- [ ] o1 a une fenêtre de contexte plus petite
- [ ] o1 est open-source contrairement à GPT-4

> Les modèles **reasoning** (o1, o3, DeepSeek-R1, Claude 3.7 Sonnet) génèrent une *chain-of-thought interne* avant la
> réponse finale. Cette phase de réflexion prolongée améliore drastiquement les performances sur les tâches de
> raisonnement complexe.

---
type: single
timer: 20
difficulty: hard
tags: [ia, llm]
---

## Que mesure la "perplexité" (perplexity) lors de l'évaluation d'un LLM ?

- [ ] Le nombre de paramètres du modèle
- [x] L'incertitude du modèle à prédire le token suivant
- [ ] La vitesse d'inférence en tokens/s
- [ ] Le coût d'entraînement en GPU-heures

> La **perplexité** = exponentielle de la cross-entropy loss. Elle mesure la "surprise" du modèle face à un texte test.
> Une perplexité basse indique que le modèle prédit bien le corpus — c'est une métrique d'évaluation intrinsèque.

---
type: single
timer: 20
difficulty: easy
tags: [prompt]
---

## Quelle technique consiste à inclure des exemples entrée/sortie directement dans le prompt ?

- [ ] Zero-shot
- [x] Few-shot prompting
- [ ] Chain-of-Thought
- [ ] Self-Consistency

> **Few-shot prompting** : fournir 1 ou plusieurs exemples ("shots") dans le prompt pour montrer le format et le
> comportement attendu, sans modifier les poids du modèle.

---
type: single
timer: 20
difficulty: medium
tags: [prompt]
---

## Quelle technique améliore le raisonnement d'un LLM en lui demandant d'expliquer ses étapes intermédiaires ?

- [ ] RAG
- [ ] Tree of Thought
- [x] Chain-of-Thought
- [ ] RLHF

> **Chain-of-Thought (CoT)** : en ajoutant "pense étape par étape" ou en montrant des exemples de raisonnement
> décomposé, le LLM produit des résultats nettement meilleurs sur des tâches de math, logique et code.

---
type: single
timer: 20
difficulty: medium
tags: [prompt]
---

## Quel est le rôle du System Prompt dans l'API Claude ou OpenAI ?

- [ ] Injecter uniquement des données RAG
- [x] Définir le persona, les règles et le contexte du modèle
- [ ] Spécifier la température d'inférence
- [ ] Lister exclusivement les outils disponibles

> Le **system prompt** est traité avant tous les messages utilisateur. Il définit l'identité, les contraintes
> comportementales et le contexte global de l'assistant — il influence l'ensemble de la conversation.

---
type: single
timer: 20
difficulty: hard
tags: [prompt]
---

## Qu'est-ce qu'une attaque de "prompt injection" ?

- [ ] L'injection de variables dynamiques dans un template de prompt
- [x] Une attaque qui fait ignorer les instructions système via des inputs malveillants
- [ ] Une technique d'optimisation automatique des prompts
- [ ] L'ajout de documents dans la fenêtre de contexte

> **Prompt injection** : un acteur malveillant insère des instructions dans les données traitées par l'agent (ex:
> document, email) pour détourner son comportement et contourner le system prompt ("Ignore previous instructions...").

---
type: single
timer: 20
difficulty: easy
tags: [context]
---

## Que désigne la "context window" (fenêtre de contexte) d'un LLM ?

- [ ] La taille de la base de données vectorielle
- [x] Le nombre max de tokens traités en une seule inférence
- [ ] La durée maximale d'une session API
- [ ] La mémoire persistante entre sessions

> La **context window** = quantité maximale de tokens (prompt + réponse) visibles simultanément par le modèle. Ex :
> Claude 3.5 Sonnet ≈ 200k tokens, GPT-4o ≈ 128k tokens.

---
type: single
timer: 20
difficulty: medium
tags: [context]
---

## Quel phénomène décrit la baisse de performance quand l'info critique est au milieu d'un long contexte ?

- [ ] Context poisoning
- [x] Lost in the middle
- [ ] Attention collapse
- [ ] Token overflow

> **"Lost in the middle"** (Liu et al., 2023) : les LLM performent mieux quand l'information importante est placée en
> début ou en fin de contexte. L'info enfouie au milieu est souvent ignorée.

---
type: single
timer: 20
difficulty: medium
tags: [context]
---

## Quelle stratégie permet de gérer des conversations très longues qui dépassent la context window ?

- [ ] Augmenter la température du modèle
- [x] Sliding window + résumé compressé
- [ ] Réduire max_tokens
- [ ] Passer à un modèle plus petit

> **Sliding window + summarization** : on conserve les N derniers messages + un résumé compressé de l'historique, créant
> une "mémoire longue" sans jamais dépasser la context window.

---
type: single
timer: 20
difficulty: hard
tags: [context]
---

## Qu'est-ce que le "KV Cache" dans l'inférence d'un LLM ?

- [ ] Un cache Redis pour les résultats d'API
- [x] La mise en cache des Key/Value des préfixes communs
- [ ] Un cache de vecteurs d'embeddings
- [ ] Un cache HTTP pour les requêtes LLM

> **KV Cache** : lors de la génération auto-régressive, les matrices Key/Value calculées pour le préfixe fixe sont mises
> en cache. Évite de les recalculer à chaque nouveau token — réduit drastiquement la latence et le coût (Prompt Caching
> chez Anthropic, jusqu'à -90% sur les tokens cached).

---
type: single
timer: 20
difficulty: easy
tags: [agents]
---

## Dans l'architecture d'un agent IA, que désigne le "tool use" / "function calling" ?

- [ ] La capacité du modèle à se fine-tuner lui-même
- [x] La capacité du LLM à invoquer des fonctions/APIs externes
- [ ] Le mécanisme de mémoire long-terme
- [ ] Le système de routing entre plusieurs agents

> **Tool use / Function calling** : le LLM peut décider d'appeler des fonctions définies (API REST, recherche web,
> exécution de code, BDD...) et intégrer les résultats dans son raisonnement pour produire sa réponse finale.

---
type: single
timer: 20
difficulty: medium
tags: [agents]
---

## Qu'est-ce que le pattern "ReAct" dans le contexte des agents LLM ?

- [ ] Un framework React.js pour les UIs d'agents
- [x] Un pattern Reasoning + Acting alternant réflexion et actions
- [ ] Un algorithme de reinforcement learning
- [ ] Un protocole de communication inter-agents

> **ReAct** (Yao et al., 2022) = Reasoning + Acting : l'agent alterne entre *Thought* (raisonnement interne), *Action*
> (appel outil) et *Observation* (résultat), formant une boucle itérative jusqu'à la réponse finale.

---
type: single
timer: 20
difficulty: medium
tags: [agents]
---

## Que signifie MCP dans l'écosystème agents IA ?

- [ ] Multi-Chain Processing
- [x] Model Context Protocol
- [ ] Memory & Context Pipeline
- [ ] Multi-Component Planning

> **Model Context Protocol (MCP)** — Anthropic, 2024 : protocole open-source standardisant la connexion entre LLM et
> serveurs de ressources (outils, données). Permet l'interopérabilité des agents avec n'importe quel fournisseur de
> services.

---
type: single
timer: 20
difficulty: hard
tags: [agents]
---

## Dans un système multi-agents, quelle est la différence entre un orchestrateur et un "swarm" ?

- [ ] Le swarm est systématiquement plus rapide
- [x] L'orchestrateur centralise le contrôle ; le swarm est décentralisé
- [ ] Le swarm utilise toujours plus d'agents
- [ ] L'orchestrateur ne peut gérer qu'un seul sous-agent

> **Orchestrateur** = contrôle centralisé, un LLM principal planifie et délègue aux sous-agents. **Swarm** =
> décentralisé, chaque agent prend ses décisions localement, la coordination émerge des interactions (ex: OpenAI Swarm,
> AutoGen).

---
type: single
timer: 20
difficulty: easy
tags: [coding]
---

## Quel outil CLI d'Anthropic permet d'utiliser Claude dans le terminal pour le développement ?

- [ ] Claude Studio
- [x] Claude Code
- [ ] Claude Terminal
- [ ] Claude Dev

> **Claude Code** : outil CLI d'Anthropic qui intègre Claude dans le terminal. Il peut lire les fichiers, exécuter des
> commandes bash, modifier du code et interagir avec Git de façon autonome dans votre repo.

---
type: single
timer: 20
difficulty: medium
tags: [coding]
---

## En agentic coding (Claude Code, Cursor...), quel fichier définit les conventions du projet ?

- [ ] .env / config.json / settings.yml
- [x] CLAUDE.md / CONVENTIONS.md / .cursorrules
- [ ] package.json / package-lock.json / yarn.lock
- [ ] Dockerfile / docker-compose.yml / .dockerignore

> Des fichiers comme **CLAUDE.md** (Claude Code), **.cursorrules** (Cursor) ou **CONVENTIONS.md** servent de "mémoire
> projet" : l'agent les lit au démarrage pour respecter l'architecture, les patterns de code et les règles métier.

---
type: single
timer: 20
difficulty: medium
tags: [coding]
---

## Quelle approche consiste à rédiger une spécification détaillée AVANT de générer du code avec un agent IA ?

- [ ] Vibe coding
- [x] Spec-Driven Development
- [ ] TDD classique
- [ ] Mob programming

> **Spec-Driven Development** : rédiger un PRD ou SPEC.md exhaustif en amont permet à l'agent de rester aligné sur
> l'intention, réduit les hallucinations architecturales et facilite la validation des livrables.

---
type: single
timer: 20
difficulty: hard
tags: [coding]
---

## Qu'est-ce que le "vibe coding" et sa principale limite en production ?

- [ ] Une méthode agile basée sur l'ambiance d'équipe
- [x] Générer du code par prompts sans le relire — dette technique invisible
- [ ] Un style de pair programming asynchrone
- [ ] Un framework de test basé sur l'expérience utilisateur

> **Vibe coding** (Karpathy, 2025) : générer du code sans le comprendre ni le relire, guidé uniquement par des prompts.
> Risques : *dette technique invisible*, vulnérabilités de sécurité non détectées, code impossible à maintenir ou
> déboguer.

---
type: single
timer: 20
difficulty: easy
tags: [rag]
---

## Que signifie l'acronyme RAG ?

- [ ] Rapid API Generation
- [x] Retrieval-Augmented Generation
- [ ] Random Adaptive Gradient
- [ ] Recursive Attention Graph

> **RAG = Retrieval-Augmented Generation** : enrichir la génération d'un LLM avec des documents récupérés dynamiquement
> depuis une base de connaissances, sans modifier les poids du modèle (pas de fine-tuning).

---
type: single
timer: 20
difficulty: medium
tags: [rag]
---

## Quelle est la fonction principale d'un modèle d'embedding dans un pipeline RAG ?

- [ ] Compresser et résumer les PDF
- [x] Convertir le texte en vecteurs sémantiques
- [ ] Générer la réponse finale de l'assistant
- [ ] Chiffrer les données stockées en base

> Un **embedding model** (ex: text-embedding-3-small, nomic-embed-text) transforme le texte en vecteurs denses dans un
> espace latent. La similarité cosinus entre vecteurs permet une *recherche sémantique* bien au-delà du keyword
> matching.

---
type: single
timer: 20
difficulty: medium
tags: [rag]
---

## Quelle extension PostgreSQL est couramment utilisée pour stocker et interroger des vecteurs d'embeddings ?

- [ ] Redis Vectors
- [ ] Elasticsearch
- [x] pgvector
- [ ] Pinecone uniquement

> **pgvector** : extension PostgreSQL ajoutant un type vectoriel et les opérateurs de similarité (cosine, L2, inner
> product). Parfaitement intégré avec **Supabase** pour construire un RAG sans infrastructure vectorielle dédiée.

---
type: single
timer: 20
difficulty: hard
tags: [rag]
---

## Qu'est-ce que le "Hybrid Search" dans un RAG et pourquoi est-il souvent supérieur à la recherche vectorielle seule ?

- [ ] Rechercher simultanément dans plusieurs LLM
- [x] Combiner recherche dense + sparse via RRF
- [ ] Une technique de chunking adaptative
- [ ] Chercher en parallèle dans plusieurs bases vectorielles

> **Hybrid Search** = dense (sémantique) + sparse (BM25/TF-IDF), fusionnés via *Reciprocal Rank Fusion (RRF)* ou un
> re-ranker. Capture à la fois la proximité sémantique ET les correspondances exactes (noms propres, codes, acronymes) —
> supérieur en précision sur la majorité des cas d'usage.
