---
title: Introduction à l'IA Générative
description: >
  Deck de démonstration HashQuiz : 10 questions sur les bases
  de l'IA générative, des LLM, du prompt et du RAG.
theme: default
author: Maxime Lenne
tags: [ia, llm, prompt, rag, gen-ai]
solo: true
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
