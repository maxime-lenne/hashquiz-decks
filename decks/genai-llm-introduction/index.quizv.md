---
title: Fondamentaux de l'IA Générative
description: >
  Quiz de validation du socle commun Bootcamp IA.
  Couvre les 5 modules : Bases IA Gen, LLM & Tokens,
  Prompt Engineering, RAG / Agents / MCP, Orientations.
theme: default
author: Maxime Lenne
tags: [ia, llm, prompt, rag, agents, mcp, gen-ai]
---

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

> L'article **"Attention is All You Need"** de Vaswani et al. (Google, 2017) a introduit l'architecture **Transformer**,
> qui est aujourd'hui la base de tous les LLM modernes (Claude, GPT, Gemini…).

---
type: single
timer: 20
difficulty: easy
tags: [ia, concepts]
---

## Quel est le bon ordre du plus large au plus spécifique ?

- [ ] Gen AI → IA → ML → DL
- [ ] ML → IA → Gen AI → DL
- [x] IA → ML → DL → Gen AI
- [ ] DL → Gen AI → ML → IA

> L'IA est le concept le plus large. Le ML (Machine Learning) en est un sous-ensemble. Le DL (Deep Learning) est un
> sous-ensemble du ML. La Gen AI (IA Générative, 2020+) est un sous-ensemble du DL basé sur les Transformers et le scale
> massif.

---
type: multiple
timer: 30
difficulty: easy
tags: [ia, gen-ai]
---

## Quelles sont les 3 grandes familles de modèles d'IA Générative ? (sélectionnez 3)

- [x] Modèles de diffusion
- [x] LLM (Large Language Models)
- [ ] CNN (Convolutional Neural Networks)
- [x] GAN (Generative Adversarial Networks)

> Les **3 familles** de Gen AI : **GAN** (images réalistes — deepfakes), **Modèles de diffusion** (Stable Diffusion,
> DALL-E, Midjourney), et **LLM** (texte, code, raisonnement — Claude, GPT). Les CNN sont des réseaux de classification,
> pas génératifs.

---
type: single
timer: 20
difficulty: medium
tags: [ia, transformer]
---

## Quelle propriété clé de l'architecture Transformer a rendu les LLM possibles ?

- [ ] Le traitement séquentiel token par token
- [ ] L'utilisation exclusive de données labellisées
- [x] Le mécanisme d'attention et le traitement parallèle
- [ ] La réduction de la taille des réseaux de neurones

> Le **mécanisme d'attention** (self-attention) permet à chaque token de "regarder" tous les autres simultanément, en
> **parallèle**. Contrairement aux RNN (séquentiels), le Transformer peut traiter l'intégralité de la séquence en une
> passe, ce qui permet le scale massif.

---
type: single
timer: 20
difficulty: easy
tags: [ia, entrainement]
---

## Que signifie RLHF dans l'entraînement des LLM ?

- [ ] Rapid Learning from High-quality Features
- [ ] Recursive Language Hyperparameter Fitting
- [x] Reinforcement Learning from Human Feedback
- [ ] Robust LLM Hyperparameter Fine-tuning

> **RLHF** = Reinforcement Learning from Human Feedback. C'est la 3e phase d'entraînement où des humains classent les
> réponses du modèle pour l'aligner sur des comportements utiles, inoffensifs et honnêtes. C'est ce qui transforme un
> modèle brut en assistant utilisable.

---
type: single
timer: 20
difficulty: medium
tags: [ia, concepts]
---

## Un LLM est dit "non-déterministe". Qu'est-ce que cela signifie concrètement ?

- [ ] Le modèle peut refuser de répondre à certaines questions
- [ ] Le modèle change de comportement selon l'heure de la journée
- [x] Le même prompt peut produire des réponses différentes à chaque fois
- [ ] Le modèle ne peut pas effectuer de calculs mathématiques

> La **non-déterminisme** vient du paramètre de **température** qui introduit de l'aléatoire dans la sélection du
> prochain token. `temperature=0` → résultat reproductible. `temperature=1` → réponses variées. C'est une
> caractéristique, pas un bug.

---
type: single
timer: 20
difficulty: medium
tags: [ia, limites]
---

## Qu'est-ce qu'une "hallucination" dans le contexte des LLM ?

- [ ] Un bug qui fait planter le modèle
- [ ] Une réponse trop longue et répétitive
- [ ] Un refus de répondre pour des raisons éthiques
- [x] Une réponse fausse présentée avec confiance comme vraie

> L'**hallucination** = le modèle génère une information fausse (date, citation, fait) en la présentant avec assurance,
> car il n'a pas de mécanisme de vérification interne. "Il ne sait pas ce qu'il ne sait pas." Toujours vérifier les
> informations factuelles sensibles.

---
type: single
timer: 25
difficulty: medium
tags: [llm, tokens]
---

## Quelle est l'approximation correcte pour la relation entre tokens et caractères en français ?

- [ ] 1 token = 1 caractère
- [ ] 1 token = 1 mot
- [x] 1 token ≈ 3-4 caractères
- [ ] 1 token = 1 phrase

> Un **token** est une unité de texte (sous-mot, mot ou fragment). En moyenne, 1 token ≈ **4 caractères** en anglais, un
> peu moins en français (les langues latines tokenisent moins efficacement). "extraordinaire" peut valoir 3-4 tokens.
> Les prix des APIs sont calculés en tokens.

---
type: single
timer: 20
difficulty: medium
tags: [llm, contexte]
---

## Que représente la "fenêtre de contexte" d'un LLM ?

- [ ] La taille maximale du fichier d'entraînement
- [ ] Le nombre de langues que le modèle peut comprendre
- [x] Tout ce que le modèle "voit" à un instant donné
- [ ] La limite de tokens qu'un utilisateur peut envoyer par jour

> La **fenêtre de contexte** = la "mémoire de travail" du modèle : system prompt + historique de conversation + message
> actuel. Ce qui n'est pas dans la fenêtre n'existe pas pour le modèle. Tailles actuelles : 128K (GPT-4o), 1M (Claude
> Sonnet 4.6, Gemini Pro).

---
type: single
timer: 20
difficulty: easy
tags: [llm, tokens]
---

## Quel paramètre contrôle la "créativité" ou la variabilité des réponses d'un LLM ?

- [ ] Context window
- [ ] Fine-tuning rate
- [ ] Batch size
- [x] Température

> La **température** contrôle l'aléatoire dans la sélection du prochain token. `temperature=0` → résultat toujours
> identique (déterministe). `temperature=1` → réponses variées et créatives. Utilisez 0 pour
> l'extraction/classification, 0.7-1 pour la créativité.

---
type: single
timer: 25
difficulty: medium
tags: [llm, modeles]
---

## Quelle est la principale différence entre un LLM et un SLM ?

- [ ] Les SLM ne peuvent pas comprendre le français
- [ ] Les LLM sont open source, les SLM sont propriétaires
- [x] Les SLM sont plus petits, peuvent tourner en local et coûtent moins cher
- [ ] Les SLM sont plus récents et plus performants que les LLM

> **LLM** (Large, 70B-1T+ paramètres) = très capables, cloud uniquement, coûteux. **SLM** (Small, 1B-30B paramètres) =
> plus légers, peuvent tourner sur un laptop ou téléphone, coût nul. Tendance 2025 : les SLM se rapprochent des LLM sur
> des tâches ciblées (distillation).

---
type: single
timer: 20
difficulty: medium
tags: [llm, cout]
---

## Dans la facturation des LLM, quel type de tokens est le plus cher ?

- [ ] Les tokens d'input (ce qu'on envoie)
- [x] Les tokens d'output (ce que le modèle génère)
- [ ] Les deux coûtent exactement la même chose
- [ ] Le coût dépend de la langue utilisée

> Les tokens d'**output** (générés par le modèle) coûtent en moyenne **3 à 5 fois plus cher** que les tokens d'input.
> Implication : demander des réponses concises ("Réponds en 3 points maximum") est à la fois plus lisible et moins
> coûteux.

---
type: single
timer: 20
difficulty: easy
tags: [prompt, anatomie]
---

## Quelles sont les 4 composantes d'un prompt bien structuré ?

- [ ] Titre, corps, conclusion, sources
- [x] Rôle, contexte, tâche, contraintes/format
- [ ] Langue, ton, longueur, exemples
- [ ] Objectif, données, outils, résultat attendu

> L'**anatomie** d'un bon prompt : **Rôle** (persona de l'IA), **Contexte** (informations nécessaires), **Tâche** (ce
> qu'elle doit faire), **Contraintes/Format** (longueur, ton, structure de sortie). Ce cadre garantit des réponses
> précises et directement utilisables.

---
type: single
timer: 20
difficulty: easy
tags: [prompt, patterns]
---

## Quelle technique consiste à inclure des exemples entrée/sortie directement dans le prompt ?

- [ ] Zero-shot
- [x] Few-shot prompting
- [ ] Chain of thought
- [ ] System prompting

> **Few-shot prompting** : fournir 1 ou plusieurs exemples ("shots") dans le prompt pour montrer le format attendu.
> Idéal pour calibrer la sortie (ex : montrer 2 exemples JSON pour obtenir du JSON). Contraste avec **zero-shot**
> (instruction seule, sans exemple).

---
type: single
timer: 25
difficulty: medium
tags: [prompt, patterns]
---

## Que fait concrètement la technique "Chain of Thought" ?

- [ ] Elle connecte plusieurs LLM ensemble
- [ ] Elle divise le prompt en plusieurs requêtes automatiquement
- [x] Elle demande au modèle de montrer son raisonnement étape par étape avant de conclure
- [ ] Elle génère plusieurs réponses en parallèle et choisit la meilleure

> **Chain of Thought** = ajouter "pense étape par étape" dans le prompt. Le modèle "montre son travail" avant de donner
> la réponse finale. Cette technique peut doubler la qualité sur des problèmes complexes (maths, logique, code) car elle
> réduit les raccourcis de raisonnement.

---
type: single
timer: 20
difficulty: medium
tags: [prompt, system]
---

## Quelle est la différence entre un "system prompt" et un "user prompt" ?

- [ ] Le system prompt est en anglais, le user prompt dans la langue de l'utilisateur
- [ ] Le system prompt est envoyé après chaque message utilisateur
- [x] Le system prompt fixe les règles de l'IA, le user prompt est ce que l'utilisateur tape
- [ ] Les deux sont identiques, c'est juste une question de nomenclature

> Le **system prompt** = "notice d'instructions" invisible à l'utilisateur final, définie par le développeur (rôle,
> contraintes, personnalité). Le **user prompt** = ce que l'utilisateur tape à chaque tour. Claude.ai, ChatGPT, Notion
> AI... utilisent tous un system prompt que vous ne voyez pas.

---
type: single
timer: 20
difficulty: easy
tags: [prompt, cout]
---

## Selon la "règle des 30 secondes", quand ne faut-il PAS solliciter l'IA ?

- [ ] Quand on travaille sur un projet personnel
- [ ] Quand la question est en français
- [x] Quand la tâche prend moins de 30 secondes à la main
- [ ] Quand on utilise un modèle open source

> La **règle des 30 secondes** : si une tâche (formater du JSON, renommer une variable, chercher une syntaxe basique)
> prend moins de 30 secondes manuellement, utiliser l'outil natif est plus rapide et économique. L'IA est pertinente
> pour les tâches à valeur ajoutée et répétitives.

---
type: single
timer: 20
difficulty: medium
tags: [ia, concepts]
---

## Qu'est-ce que l'inférence dans le contexte d'un LLM ?

- [ ] L'entraînement du modèle sur de nouvelles données
- [ ] Le processus de fine-tuning pour spécialiser le modèle
- [x] La génération d'une réponse par prédiction successive de tokens
- [ ] La compression du modèle pour le déploiement en local

> L'**inférence** = le processus par lequel le modèle entraîné *génère* une réponse. Le LLM prédit le token suivant de
> manière auto-régressive (chaque token dépend de tous les précédents), en répétant jusqu'à la fin de séquence. C'est
> l'étape qui coûte de l'argent (contrairement à l'entraînement).

---
type: single
timer: 25
difficulty: hard
tags: [llm, modeles]
---

## Quelle stratégie adopter pour optimiser le coût de ses appels à l'API d'un LLM ?

- [ ] Toujours utiliser le modèle le plus puissant pour garantir la qualité
- [ ] Utiliser uniquement des modèles open source locaux
- [x] Commencer par le modèle le plus léger et escalader vers des modèles plus puissants si nécessaire
- [ ] Regrouper toutes les requêtes en une seule très longue requête

> La **stratégie du modèle minimal viable** : Haiku/Flash pour les tâches simples (formatage, Q&A basique), Sonnet pour
> l'usage quotidien, Opus uniquement pour le raisonnement complexe. Haiku peut coûter 20-50x moins cher qu'Opus.
> Commencer léger, escalader si la qualité est insuffisante.

---
type: single
timer: 25
difficulty: medium
tags: [rag, concepts]
---

## Que signifie l'acronyme RAG ?

- [ ] Rapid Augmented Generation
- [ ] Recursive Agent Graph
- [x] Retrieval-Augmented Generation
- [ ] Realtime API Gateway

> **RAG** = **Retrieval-Augmented Generation**. Le principe : avant de générer une réponse, le système *retrieve*
> (cherche) les documents pertinents dans une base vectorielle, les *augmente* (injecte dans le prompt), puis le LLM
> *generate* une réponse informée. Solution aux LLM à connaissance figée.

---
type: single
timer: 25
difficulty: medium
tags: [rag, embeddings]
---

## Dans un système RAG, à quoi servent les "embeddings" ?

- [ ] À accélérer la génération de tokens
- [ ] À compresser les documents pour réduire les coûts
- [x] À encoder le sens d'un texte en vecteur pour la recherche sémantique
- [ ] À traduire les documents dans la langue du modèle

> Les **embeddings** convertissent un texte en **vecteur numérique** représentant son sens. Textes similaires → vecteurs
> proches dans l'espace. Cela permet la **recherche sémantique** : trouver des documents pertinents par sens, pas par
> mots-clés exacts. Base technique de tout RAG.

---
type: single
timer: 20
difficulty: easy
tags: [rag, usage]
---

## Quel problème des LLM le RAG résout-il principalement ?

- [ ] Les hallucinations sur tous les sujets
- [ ] La lenteur de génération des réponses
- [ ] Le coût élevé des tokens d'output
- [x] La connaissance figée et l'accès à vos données internes

> Le RAG adresse deux limites : la **connaissance figée** (date de coupure) et l'**absence de mémoire** sur vos
> documents internes (politiques RH, documentation produit, emails…). Le modèle ne change pas — on lui donne les bonnes
> informations au moment de la question.

---
type: single
timer: 20
difficulty: easy
tags: [agents, concepts]
---

## Quelle est la différence fondamentale entre un chatbot et un agent IA ?

- [ ] Un agent IA parle plusieurs langues, un chatbot une seule
- [ ] Un chatbot est plus intelligent qu'un agent IA
- [x] Un chatbot répond à des questions, un agent exécute des actions
- [ ] Un agent IA est toujours plus coûteux qu'un chatbot

> **Chatbot** : réactif, répond à des questions, ne prend pas d'initiative. **Agent IA** : autonome, planifie les
> étapes, exécute des actions (APIs, terminal, recherche), s'adapte selon les résultats. Formule : **Agent = LLM +
> Outils + Boucle d'exécution**.

---
type: single
timer: 20
difficulty: medium
tags: [agents, formule]
---

## Quelle formule résume le mieux la composition d'un agent IA ?

- [ ] Agent = LLM + Interface + Base de données
- [ ] Agent = Prompt + Réponse + Action
- [x] Agent = LLM + Outils + Boucle d'exécution
- [ ] Agent = Modèle + Fine-tuning + Déploiement

> La formule est **Agent = LLM + Outils + Boucle d'exécution**. Le LLM est le "cerveau", les outils lui donnent des
> capacités d'action (APIs, terminal, fonctions), et la boucle lui permet de recommencer jusqu'à atteindre l'objectif.
> Claude Code est un exemple concret : il lit du code, exécute des commandes, et réitère.

---
type: single
timer: 25
difficulty: medium
tags: [agents, react]
---

## Que décrit le pattern "ReAct" dans le contexte des agents IA ?

- [ ] Une bibliothèque JavaScript pour créer des interfaces d'agents
- [ ] Un pattern de déploiement (React = deploy en plusieurs étapes)
- [x] Une boucle Reason → Act → Observe que l'agent répète jusqu'à atteindre l'objectif
- [ ] Un type de modèle spécialisé dans la réaction en temps réel

> **ReAct** (Reasoning + Acting) = boucle cyclique : **Reason** (que faire ?), **Act** (exécuter l'outil choisi),
> **Observe** (analyser le résultat). Si l'objectif n'est pas atteint → recommence. C'est le pattern de base de tous les
> agents modernes (Claude Code, Cursor, Devin…).

---
type: single
timer: 20
difficulty: easy
tags: [mcp, concepts]
---

## Quelle analogie résume le mieux le rôle du MCP (Model Context Protocol) ?

- [ ] Le GPS de l'IA
- [ ] Le Wi-Fi de l'IA
- [x] L'USB-C de l'IA
- [ ] Le système d'exploitation de l'IA

> **MCP = "L'USB-C de l'IA"**. Avant l'USB-C, chaque appareil avait son câble propriétaire. Avant MCP, chaque outil IA
> avait ses propres intégrations custom. MCP = un protocole universel : un serveur MCP fonctionne avec Claude Code,
> Cursor, et tout client compatible.

---
type: single
timer: 20
difficulty: easy
tags: [mcp, histoire]
---

## Qui a lancé le Model Context Protocol (MCP) et quand ?

- [ ] OpenAI, janvier 2024
- [ ] Google, mars 2024
- [x] Anthropic, novembre 2024
- [ ] Meta, juin 2025

> **Anthropic** a lancé MCP en **open source en novembre 2024**. OpenAI l'a adopté en mars 2025. Aujourd'hui, c'est le
> standard de facto pour connecter des agents IA à des sources de données externes.

---
type: single
timer: 25
difficulty: medium
tags: [mcp, architecture]
---

## Dans l'architecture MCP, quels sont les 3 composants principaux ?

- [ ] Prompt, Response, Action
- [ ] Model, Context, Protocol
- [x] Host, Client, Server
- [ ] Input, Middleware, Output

> L'architecture MCP : **Host** (l'app IA : Claude Code, Cursor) → **Client** (composant logique interne qui porte
> une connexion) → **Server** (source de données : GitHub, Figma, Chrome DevTools, Supabase…). Les 3 primitives d'un
> serveur MCP : **Tools** (actions), **Resources** (données), **Prompts** (templates).

---
type: multiple
timer: 30
difficulty: medium
tags: [mcp, outils]
---

## Parmi ces outils, lesquels sont des serveurs MCP couramment utilisés ? (sélectionnez 3)

- [x] GitHub (code, PRs, issues)
- [ ] React (framework JavaScript)
- [x] Context7 (documentation live)
- [x] Figma (design ↔ code)

> **Context7**, **GitHub** et **Figma** sont des serveurs MCP essentiels. Context7 fournit la documentation à jour des
> librairies. GitHub permet de lire/écrire du code et des PRs. Figma permet d'extraire les specs de design. React est un
> framework frontend, pas un serveur MCP.
