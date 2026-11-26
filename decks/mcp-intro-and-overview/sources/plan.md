# MCP intro and overview — Plan

**Target questions:** 20 (pool — la quiz affichera 10 questions tirées au hasard via `max-questions: 10`)
**Estimated duration (pool):** ~456 s (~7,6 min) · **Duration affichée (10 questions, moyenne):** ~220 s (~3,7 min)
**Language:** Français
**Difficulty mix:** 20 % easy / 60 % medium / 20 % hard
**Question types:** Majorité single-choice (~75 %) + multiple-choice pour les sujets nuancés (~25 %)
**Audience tone:** Onboarding / parties prenantes non-dev — privilégier le cadrage conceptuel (analogie USB-C, problème résolu) plutôt que les détails protocolaires

---

## Sources Used

- `01-intro.md` — Prérequis et objectifs (host/client/server, JSON-RPC, primitives, FastMCP)
- `02-bases-ia-gen.md` — Bases IA générative : Transformer, familles (GAN/Diffusion/LLM), entraînement, déterminisme, limites, modèles frontier 2025
- `02-pourquoi-mcp.md` — Problème N×M, MCP n'est pas une API, analogie USB-C
- `03-architecture.md` — Rôles Host / Client / Server, local stdio vs remote HTTP, data layer vs transport layer
- `05-rag-agents-mcp.md` — RAG (retrieve/augment/generate), Agent vs Chatbot, boucle ReAct, MCP comme « USB-C de l'IA », historique, primitives, serveurs concrets
- `structure-links.md` — Brief de cadrage (besoins d'alignement équipe, MCP vs API, MCP vs RAG)

_Aucune recherche web nécessaire : les sources couvrent largement les 20 questions ciblées._

---

## Difficulty Distribution

| Difficulty | Count | Percentage |
|------------|-------|------------|
| easy       | 4     | 20 %       |
| medium     | 12    | 60 %       |
| hard       | 4     | 20 %       |

---

## Type Distribution

| Type     | Count | Notes |
|----------|-------|-------|
| single   | 15    | Pacing rapide, focus conceptuel |
| multiple | 5     | Réservé aux énumérations (familles, limites, primitives, rôles du host, data layer) |

---

## Tag Coverage

| Tag (question-level)     | Questions                |
|--------------------------|--------------------------|
| genai                    | Q1, Q2, Q4               |
| llm-limits               | Q3, Q5                   |
| mcp-why                  | Q6, Q7, Q8, Q9           |
| usb-c                    | Q8                       |
| architecture             | Q10, Q11, Q12            |
| transport                | Q13, Q15                 |
| data-layer / json-rpc    | Q14                      |
| primitives               | Q20                      |
| rag                      | Q16                      |
| agents                   | Q17, Q18                 |
| history                  | Q19                      |

_Tags quiz-level (de la frontmatter) : `mcp`, `ai`, `llm`, `integration` — appliqués implicitement à toutes les questions._

---

## Questions

### Q1 — Année et nom de l'article fondateur des Transformers

- **Type:** single
- **Difficulty:** easy
- **Timer:** 18 s
- **Tags:** [genai, transformer, history]
- **Source:** `02-bases-ia-gen.md` (slides "Histoire IA 70 ans", "Architecture Transformer")
- **Key concept:** Identifier 2017 / « Attention is All You Need » comme le point de bascule de l'IA générative moderne.
- **Notes:** Mauvaises réponses plausibles : 2012 (AlexNet), 2022 (ChatGPT), 2020 (GPT-3).

### Q2 — Les trois familles de l'IA générative

- **Type:** multiple
- **Difficulty:** medium
- **Timer:** 25 s
- **Tags:** [genai]
- **Source:** `02-bases-ia-gen.md` (slide "Les 3 familles de l'IA Générative")
- **Key concept:** GAN, Modèles de diffusion, LLM — sélectionner les 3 bonnes parmi des distracteurs (RNN, CNN, Reinforcement Learning…).
- **Notes:** Question multiple : exactement 3 bonnes réponses.

### Q3 — Limites connues des LLM

- **Type:** multiple
- **Difficulty:** medium
- **Timer:** 25 s
- **Tags:** [llm-limits]
- **Source:** `02-bases-ia-gen.md` (slide "Limites des LLM")
- **Key concept:** Hallucination, fenêtre de contexte limitée, date de coupure, faiblesse en calcul, biais — distracteurs : « accès Internet temps réel », « parle toutes les langues parfaitement ».
- **Notes:** 4-5 bonnes réponses parmi 6-7 choix.

### Q4 — Rôle du paramètre température

- **Type:** single
- **Difficulty:** medium
- **Timer:** 22 s
- **Tags:** [genai, llm-limits]
- **Source:** `02-bases-ia-gen.md` (slide "Déterministe vs Non-déterministe")
- **Key concept:** La température contrôle le caractère déterministe/créatif des réponses (0 = reproductible, 1 = varié).
- **Notes:** Distracteurs : « contrôle la vitesse », « limite la taille du contexte », « ajuste le coût en tokens ».

### Q5 — Analogie pour exprimer la limitation d'un LLM seul

- **Type:** single
- **Difficulty:** easy
- **Timer:** 18 s
- **Tags:** [llm-limits, rag]
- **Source:** `05-rag-agents-mcp.md` (statement « Un LLM seul, c'est un expert brillant enfermé dans une pièce sans fenêtre »)
- **Key concept:** Comprendre que sans accès à des données ou outils externes, un LLM reste figé sur ses données d'entraînement.
- **Notes:** Mémorabilité de la métaphore — distracteurs : « calculatrice surpuissante », « base de données vivante ».

### Q6 — Le problème que MCP cherche à résoudre

- **Type:** single
- **Difficulty:** easy
- **Timer:** 18 s
- **Tags:** [mcp-why]
- **Source:** `02-pourquoi-mcp.md` (slide "Le problème : N × M")
- **Key concept:** Sans MCP, N apps × M services = N×M intégrations custom à maintenir.
- **Notes:** Distracteurs : « le coût des tokens », « le manque de modèles open source », « la latence des APIs LLM ».

### Q7 — MCP n'est pas une simple API

- **Type:** single
- **Difficulty:** medium
- **Timer:** 22 s
- **Tags:** [mcp-why]
- **Source:** `02-pourquoi-mcp.md` (statement "MCP n'est pas une API")
- **Key concept:** MCP est un **protocole stateful** avec lifecycle et négociation de capabilities — pas un wrapper REST.
- **Notes:** Distracteurs : « une API REST standardisée », « un format de fichier de config », « une bibliothèque Python ».

### Q8 — L'analogie USB-C

- **Type:** single
- **Difficulty:** medium
- **Timer:** 20 s
- **Tags:** [mcp-why, usb-c]
- **Source:** `05-rag-agents-mcp.md` (slide "MCP — L'USB-C de l'IA"), `02-pourquoi-mcp.md`
- **Key concept:** MCP joue pour l'IA le rôle que l'USB-C joue pour le hardware : un standard universel pour brancher n'importe quel outil à n'importe quel agent.
- **Notes:** Bonne accroche conceptuelle pour audience non-dev.

### Q9 — Combien d'intégrations à maintenir avec MCP

- **Type:** single
- **Difficulty:** hard
- **Timer:** 28 s
- **Tags:** [mcp-why, architecture]
- **Source:** `02-pourquoi-mcp.md` (slide "Avec MCP : N + M")
- **Key concept:** Avec MCP on passe de N×M intégrations à **N + M** (chaque app parle un seul protocole, chaque service expose un seul protocole).
- **Notes:** Question quantitative — distracteurs : N×M, N², 2×(N+M).

### Q10 — Les trois composants d'une architecture MCP

- **Type:** single
- **Difficulty:** easy
- **Timer:** 18 s
- **Tags:** [architecture]
- **Source:** `03-architecture.md` (slide "Trois composants")
- **Key concept:** Host / Client / Server — vocabulaire de base.
- **Notes:** Distracteurs : Frontend/Backend/DB, Proxy/Gateway/Worker, Producer/Broker/Consumer.

### Q11 — Relation Host ↔ Client ↔ Server

- **Type:** single
- **Difficulty:** medium
- **Timer:** 22 s
- **Tags:** [architecture, client]
- **Source:** `03-architecture.md` (slides "Trois composants" et "Synthèse")
- **Key concept:** 1 Host → N clients, et **1 client ↔ 1 server ↔ 1 connexion** (relation 1:1 par connexion).
- **Notes:** Confusion fréquente — distracteurs : « 1 client peut parler à plusieurs servers », « 1 host = 1 client ».

### Q12 — Rôles du Host MCP

- **Type:** multiple
- **Difficulty:** medium
- **Timer:** 25 s
- **Tags:** [architecture, host]
- **Source:** `03-architecture.md` (slide "Trois composants — rôles détaillés")
- **Key concept:** Le Host **instancie et gère les clients**, **applique les politiques** (auth, permissions, sampling) et **consolide les capacités** des servers pour le modèle.
- **Notes:** Distracteurs : « exécute les tools directement », « stocke les embeddings », « parse le JSON-RPC ».

### Q13 — Différence entre transport stdio et HTTP

- **Type:** single
- **Difficulty:** medium
- **Timer:** 25 s
- **Tags:** [transport, stdio, http]
- **Source:** `03-architecture.md` (slide "Local vs Remote")
- **Key concept:** Stdio = local, mono-client (un process par client) ; HTTP (streamable) = remote, multi-client.
- **Notes:** Distracteurs : « stdio est multi-client », « HTTP est mono-client », « les deux nécessitent OAuth ».

### Q14 — Composants du data layer MCP

- **Type:** multiple
- **Difficulty:** hard
- **Timer:** 30 s
- **Tags:** [data-layer, json-rpc, primitives]
- **Source:** `03-architecture.md` (slide "Deux couches : Data + Transport")
- **Key concept:** Data layer = **JSON-RPC 2.0**, **lifecycle** (initialize/shutdown), **capabilities negotiation**, **primitives** (tools/resources/prompts), notifications temps réel — distinguer du transport (stdio/HTTP).
- **Notes:** Distracteurs côté transport : « stdin/stdout », « OAuth », « framing HTTP », « SSE » — montrer la séparation des couches.

### Q15 — Auth recommandée pour un MCP remote

- **Type:** single
- **Difficulty:** medium
- **Timer:** 22 s
- **Tags:** [transport, http]
- **Source:** `03-architecture.md` (slide "Local vs Remote")
- **Key concept:** OAuth 2.1 est l'auth recommandée pour un MCP remote (HTTP).
- **Notes:** Distracteurs : « API Key brute », « pas d'auth nécessaire », « JWT custom », « SAML ».

### Q16 — Signification de l'acronyme RAG

- **Type:** single
- **Difficulty:** medium
- **Timer:** 20 s
- **Tags:** [rag]
- **Source:** `05-rag-agents-mcp.md` (slide "Pourquoi les LLM ont besoin de RAG")
- **Key concept:** Retrieve — Augment — Generate : récupérer les documents pertinents, augmenter le prompt, puis générer la réponse.
- **Notes:** Distracteurs : « Random Access Generation », « Recursive Agent Graph », « Retrieval And Grading ».

### Q17 — Différence fondamentale Chatbot vs Agent IA

- **Type:** single
- **Difficulty:** medium
- **Timer:** 22 s
- **Tags:** [agents]
- **Source:** `05-rag-agents-mcp.md` (slide "Agent IA vs Chatbot")
- **Key concept:** Un chatbot répond ; un agent **planifie, exécute des actions et boucle** jusqu'à atteindre l'objectif (Agent = LLM + Outils + Boucle).
- **Notes:** Distracteurs : « un agent est plus rapide », « un chatbot utilise plus de tokens », « la différence est uniquement l'UI ».

### Q18 — La boucle ReAct

- **Type:** single
- **Difficulty:** medium
- **Timer:** 22 s
- **Tags:** [agents]
- **Source:** `05-rag-agents-mcp.md` (slide "Composants d'un agent IA")
- **Key concept:** ReAct = **Reason → Act → Observe**, en boucle jusqu'à l'objectif.
- **Notes:** Distracteurs : « Read / Execute / Acknowledge / Close », « Request / Authenticate / Continue / Terminate ».

### Q19 — Date de lancement de MCP par Anthropic

- **Type:** single
- **Difficulty:** hard
- **Timer:** 28 s
- **Tags:** [history]
- **Source:** `05-rag-agents-mcp.md` (slide "MCP — L'USB-C de l'IA" / tableau historique)
- **Key concept:** Anthropic a lancé MCP en open source en **novembre 2024**, OpenAI l'a adopté en **mars 2025**.
- **Notes:** Distracteurs : juin 2024, janvier 2025, octobre 2023.

### Q20 — Les trois primitives exposées par un serveur MCP

- **Type:** multiple
- **Difficulty:** hard
- **Timer:** 28 s
- **Tags:** [primitives, architecture]
- **Source:** `01-intro.md` (objectifs) + `03-architecture.md` (slide Server) + `05-rag-agents-mcp.md` (slide "Architecture MCP")
- **Key concept:** **Tools** (actions exécutables), **Resources** (données accessibles), **Prompts** (templates réutilisables).
- **Notes:** Distracteurs côté client : « sampling », « elicitation », « roots » — utile pour tester la distinction primitives server vs primitives client.

---

## Review Checklist

- [ ] Questions cover all key topics from sources (GenAI, problème N×M, architecture, transports, RAG/Agents, primitives, historique)
- [ ] Difficulty distribution matches target (4 / 12 / 4)
- [ ] No duplicate or overly similar questions
- [ ] Tags are consistent and meaningful
- [ ] Timer values are realistic for question complexity (15-20 easy, 20-25 medium, 25-35 hard)
- [ ] Mix of single (15) and multiple (5) choice respecté
- [ ] Tone reste accessible (audience onboarding / non-dev)

---

_Plan created: 2026-05-29_
_Ready for quiz generation: [ ]_
