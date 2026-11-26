# Docker — Plan

**Target questions:** 30
**Estimated duration:** ~690 seconds (~11.5 min)
**Language:** Français
**Difficulty mix:** 30% easy (9), 40% medium (12), 30% hard (9)
**Question types:** easy = single only, medium/hard = mix single & multiple
**Audience:** Développeurs juniors (Simplon), vérification post-cours Docker

---

## Sources Used

- `pourquoi-docker.md` — Pourquoi Docker est incontournable, cas d'usage par métier
- `docker-install.md` — Installation Linux (Ubuntu/Debian) et Windows (Docker Desktop, WSL2)
- `docker-base-concepts.md` — Images, conteneurs, Dockerfile, registry, volumes, réseaux
- `docker-cheat-sheet.md` — Référence des commandes Docker

---

## Difficulty Distribution

| Difficulty | Count | Percentage |
|------------|-------|------------|
| easy       | 9     | 30%        |
| medium     | 12    | 40%        |
| hard       | 9     | 30%        |

---

## Tag Coverage

| Tag | Questions |
|-----|-----------|
| image | Q1, Q2, Q3, Q14, Q22 |
| container | Q4, Q5, Q6, Q7, Q15, Q16, Q23, Q24 |
| dockerfile | Q8, Q9, Q17, Q18, Q25, Q26 |
| registry | Q10, Q19, Q27 |
| volume | Q11, Q20, Q28 |
| network | Q12, Q21, Q29 |
| installation | Q13, Q30 |

---

## Questions

### Q1 — Qu'est-ce qu'une image Docker ?

- **Type:** single
- **Difficulty:** easy
- **Timer:** 15s
- **Tags:** [docker, image]
- **Source:** docker-base-concepts.md §1
- **Key concept:** Définition d'une image (ensemble de couches en lecture seule)
- **Notes:** Proposer des confusions classiques (conteneur, volume, réseau)

### Q2 — Commande pour lister les images locales

- **Type:** single
- **Difficulty:** easy
- **Timer:** 15s
- **Tags:** [docker, image]
- **Source:** docker-cheat-sheet.md §1
- **Key concept:** `docker images` pour lister les images locales
- **Notes:** Distracteurs : `docker ps`, `docker list`, `docker ls`

### Q3 — Commande pour télécharger une image

- **Type:** single
- **Difficulty:** easy
- **Timer:** 15s
- **Tags:** [docker, image]
- **Source:** docker-base-concepts.md §1.4
- **Key concept:** `docker pull <image>:<tag>`
- **Notes:** Distracteurs : `docker download`, `docker get`, `docker fetch`

### Q4 — Qu'est-ce qu'un conteneur Docker ?

- **Type:** single
- **Difficulty:** easy
- **Timer:** 15s
- **Tags:** [docker, container]
- **Source:** docker-base-concepts.md §2.1
- **Key concept:** Instance en cours d'exécution d'une image
- **Notes:** Distinguer image vs conteneur vs Dockerfile

### Q5 — Commande pour lister les conteneurs actifs

- **Type:** single
- **Difficulty:** easy
- **Timer:** 15s
- **Tags:** [docker, container]
- **Source:** docker-cheat-sheet.md §2
- **Key concept:** `docker ps` pour les conteneurs en cours d'exécution
- **Notes:** Distracteur : `docker ps -a` (tous, y compris arrêtés)

### Q6 — Option pour lancer un conteneur en arrière-plan

- **Type:** single
- **Difficulty:** easy
- **Timer:** 15s
- **Tags:** [docker, container]
- **Source:** docker-base-concepts.md §2.3
- **Key concept:** Option `-d` (mode détaché)
- **Notes:** Distracteurs : `-b`, `--background`, `-bg`

### Q7 — Nature éphémère des conteneurs

- **Type:** single
- **Difficulty:** easy
- **Timer:** 15s
- **Tags:** [docker, container, volume]
- **Source:** docker-base-concepts.md §2.5
- **Key concept:** Les données écrites dans un conteneur sont perdues à sa suppression
- **Notes:** Question vrai/faux style, mener vers les volumes

### Q8 — Rôle de l'instruction FROM dans un Dockerfile

- **Type:** single
- **Difficulty:** easy
- **Timer:** 15s
- **Tags:** [docker, dockerfile]
- **Source:** docker-base-concepts.md §3.2
- **Key concept:** FROM spécifie l'image de base
- **Notes:** Distracteurs : définit le port, le volume, la commande

### Q9 — Commande pour construire une image depuis un Dockerfile

- **Type:** single
- **Difficulty:** easy
- **Timer:** 15s
- **Tags:** [docker, dockerfile, image]
- **Source:** docker-cheat-sheet.md §1
- **Key concept:** `docker build -t <nom>:<tag> .`
- **Notes:** Distracteurs : `docker create`, `docker make`, `docker compile`

### Q10 — Qu'est-ce que Docker Hub ?

- **Type:** single
- **Difficulty:** medium
- **Timer:** 20s
- **Tags:** [docker, registry]
- **Source:** docker-base-concepts.md §4.2
- **Key concept:** Registre public par défaut pour stocker et distribuer des images
- **Notes:** Distinguer de GitHub, Docker Desktop, Docker Engine

### Q11 — Différence entre volume nommé et bind mount

- **Type:** single
- **Difficulty:** medium
- **Timer:** 25s
- **Tags:** [docker, volume]
- **Source:** docker-base-concepts.md §5.2
- **Key concept:** Volume nommé géré par Docker vs bind mount pointant vers un dossier hôte
- **Notes:** Question comparative, bien expliquer les deux dans les choix

### Q12 — Types de réseaux Docker

- **Type:** multiple
- **Difficulty:** medium
- **Timer:** 25s
- **Tags:** [docker, network]
- **Source:** docker-base-concepts.md §6.2
- **Key concept:** bridge, host, none, overlay sont des types de réseaux Docker
- **Notes:** Ajouter des distracteurs : `nat`, `tunnel`, `mesh`

### Q13 — Prérequis pour Docker Desktop sur Windows

- **Type:** single
- **Difficulty:** medium
- **Timer:** 20s
- **Tags:** [docker, installation]
- **Source:** docker-install.md §2.1
- **Key concept:** WSL 2 nécessaire pour Docker Desktop sur Windows
- **Notes:** Distracteurs : Hyper-V seul, VirtualBox, VMware

### Q14 — Système de couches (layers) des images

- **Type:** single
- **Difficulty:** medium
- **Timer:** 25s
- **Tags:** [docker, image]
- **Source:** docker-base-concepts.md §1.2
- **Key concept:** Chaque instruction Dockerfile crée une couche, Union File System les fusionne
- **Notes:** Question sur pourquoi les images partagent des couches (efficacité espace disque)

### Q15 — Options de la commande docker run

- **Type:** multiple
- **Difficulty:** medium
- **Timer:** 25s
- **Tags:** [docker, container]
- **Source:** docker-base-concepts.md §2.3
- **Key concept:** Options -d, -p, -v, --name, --env
- **Notes:** Demander quelles options sont valides parmi une liste

### Q16 — Accéder à un shell dans un conteneur en cours d'exécution

- **Type:** single
- **Difficulty:** medium
- **Timer:** 20s
- **Tags:** [docker, container]
- **Source:** docker-cheat-sheet.md §2
- **Key concept:** `docker exec -it <conteneur> bash`
- **Notes:** Distracteurs : `docker ssh`, `docker connect`, `docker attach`

### Q17 — Différence entre CMD et ENTRYPOINT

- **Type:** single
- **Difficulty:** medium
- **Timer:** 25s
- **Tags:** [docker, dockerfile]
- **Source:** docker-base-concepts.md §3.2
- **Key concept:** CMD = commande par défaut (remplaçable), ENTRYPOINT = point d'entrée fixe
- **Notes:** Question classique, bien formuler les nuances

### Q18 — Bonnes pratiques Dockerfile : minimiser les couches

- **Type:** single
- **Difficulty:** medium
- **Timer:** 25s
- **Tags:** [docker, dockerfile]
- **Source:** docker-base-concepts.md §3.3
- **Key concept:** Combiner les commandes RUN pour réduire le nombre de couches
- **Notes:** Montrer un exemple avec && vs instructions séparées

### Q19 — Étapes pour pousser une image vers un registre

- **Type:** multiple
- **Difficulty:** medium
- **Timer:** 25s
- **Tags:** [docker, registry]
- **Source:** docker-base-concepts.md §4.4-4.5
- **Key concept:** tag + login + push sont les 3 étapes nécessaires
- **Notes:** Demander les étapes correctes parmi une liste

### Q20 — Commande pour créer un volume nommé

- **Type:** single
- **Difficulty:** medium
- **Timer:** 20s
- **Tags:** [docker, volume]
- **Source:** docker-cheat-sheet.md §3
- **Key concept:** `docker volume create <nom>`
- **Notes:** Distracteurs : `docker create volume`, `docker volume new`, `docker volume add`

### Q21 — Communication entre conteneurs par nom DNS

- **Type:** single
- **Difficulty:** medium
- **Timer:** 25s
- **Tags:** [docker, network]
- **Source:** docker-base-concepts.md §6.4
- **Key concept:** Conteneurs sur un même réseau nommé se joignent par nom DNS
- **Notes:** Insister sur réseau nommé (pas le bridge par défaut)

### Q22 — Images officielles vs communautaires

- **Type:** single
- **Difficulty:** hard
- **Timer:** 30s
- **Tags:** [docker, image, registry]
- **Source:** docker-base-concepts.md §1.3
- **Key concept:** Critères de choix, maintenance, sécurité des images officielles
- **Notes:** Scénario : quelle image choisir pour la production ?

### Q23 — Limiter les ressources d'un conteneur

- **Type:** multiple
- **Difficulty:** hard
- **Timer:** 30s
- **Tags:** [docker, container]
- **Source:** docker-base-concepts.md §2.4
- **Key concept:** Options -m (mémoire) et --cpus pour limiter les ressources
- **Notes:** Identifier les bonnes options parmi des distracteurs

### Q24 — Isolation des conteneurs : namespaces et cgroups

- **Type:** multiple
- **Difficulty:** hard
- **Timer:** 30s
- **Tags:** [docker, container]
- **Source:** docker-base-concepts.md §2.1, §2.4
- **Key concept:** Namespaces isolent les vues système, cgroups limitent les ressources
- **Notes:** Quels mécanismes Linux Docker utilise pour l'isolation

### Q25 — Différence entre COPY et ADD dans un Dockerfile

- **Type:** single
- **Difficulty:** hard
- **Timer:** 30s
- **Tags:** [docker, dockerfile]
- **Source:** docker-base-concepts.md §3.2
- **Key concept:** COPY copie des fichiers, ADD supporte URLs et décompression d'archives
- **Notes:** Bonne pratique : préférer COPY sauf besoin spécifique

### Q26 — Rôle du fichier .dockerignore

- **Type:** single
- **Difficulty:** hard
- **Timer:** 25s
- **Tags:** [docker, dockerfile]
- **Source:** docker-base-concepts.md §3.3
- **Key concept:** Exclure des fichiers du contexte de build (node_modules, logs, .env)
- **Notes:** Analogie avec .gitignore, impact sur la taille de l'image

### Q27 — Registre privé : solutions disponibles

- **Type:** multiple
- **Difficulty:** hard
- **Timer:** 30s
- **Tags:** [docker, registry]
- **Source:** docker-base-concepts.md §4.3
- **Key concept:** registry:2 (self-hosted), ECR, GCR/Artifact Registry, ACR
- **Notes:** Identifier les vrais services de registre parmi des distracteurs

### Q28 — Scénario : persistance de données d'une base de données

- **Type:** single
- **Difficulty:** hard
- **Timer:** 30s
- **Tags:** [docker, volume, container]
- **Source:** docker-base-concepts.md §5.1, §5.4
- **Key concept:** Utiliser un volume nommé pour les données persistantes (BDD)
- **Notes:** Scénario pratique : que se passe-t-il sans volume ? Quelle solution ?

### Q29 — Réseau overlay : cas d'usage

- **Type:** single
- **Difficulty:** hard
- **Timer:** 30s
- **Tags:** [docker, network]
- **Source:** docker-base-concepts.md §6.2
- **Key concept:** Overlay permet la communication inter-hôte (Swarm, orchestration)
- **Notes:** Distinguer de bridge (même hôte), host (partage pile réseau)

### Q30 — Ajout de l'utilisateur au groupe docker sur Linux

- **Type:** single
- **Difficulty:** hard
- **Timer:** 25s
- **Tags:** [docker, installation]
- **Source:** docker-install.md §1.6
- **Key concept:** `sudo usermod -aG docker $USER` pour éviter sudo
- **Notes:** Pourquoi c'est recommandé, quelle commande exacte, que faire après

---

## Review Checklist

- [x] Questions cover all key topics from sources
- [x] Difficulty distribution matches target (9/12/9)
- [x] No duplicate or overly similar questions
- [x] Tags are consistent and meaningful
- [x] Timer values are realistic for question complexity
- [x] Mix of single and multiple choice in medium/hard
- [x] Easy questions are single-choice only
- [x] Docker Compose excluded (hors scope)
- [x] Adapted for junior developer audience (Simplon, post-course check)

---

_Plan created: 2026-04-25_
_Ready for quiz generation: [ ]_
