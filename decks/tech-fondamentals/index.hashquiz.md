---
title: Les fondamentaux tech
description: >
  Les bases techniques à connaître, en 2 ou 3 questions par sujet : Git, API, bases de données, Docker,
  scraping, no-code, JSON / YAML / Markdown, terminal, Bash, CI/CD, outils de vérification,
  observabilité, cloud et HTML.
theme: default
author: Maxime Lenne
tags: [git, api, bdd, docker, scraping, no-code, formats, terminal, bash, ci-cd, verification, observabilite, cloud, html]
solo: true
---

---
type: single
timer: 20
difficulty: easy
tags: [git]
---

## Quelle commande Git enregistre les modifications indexées dans l'historique ?

- [x] `git commit`
- [ ] `git push`
- [ ] `git add`
- [ ] `git merge`

> `git add` indexe les modifications, `git commit` les enregistre dans l'historique local, `git push` les envoie
> au dépôt distant.

---
type: single
timer: 20
difficulty: medium
tags: [git]
---

## Que fait `git pull` ?

- [ ] Il envoie les commits locaux vers le dépôt distant
- [x] Il récupère les commits distants et les intègre à la branche
- [ ] Il crée une copie locale complète d'un dépôt distant
- [ ] Il annule le dernier commit de la branche locale

> `git pull` = `git fetch` (récupérer les commits distants) + `git merge` (ou `rebase`) dans la branche courante.
> `git clone` crée la copie locale, `git push` envoie les commits.

---
type: single
timer: 20
difficulty: easy
tags: [git]
---

## Quel fichier liste les fichiers que Git ne doit pas suivre ?

- [ ] `.gitconfig`
- [ ] `.gitkeep`
- [x] `.gitignore`
- [ ] `.gitattributes`

> `.gitignore` contient les motifs des fichiers à ne pas versionner : `node_modules/`, `.env`, fichiers de build…

---
type: single
timer: 20
difficulty: easy
tags: [api]
---

## Que signifie l'acronyme API ?

- [x] Application Programming Interface
- [ ] Automated Program Integration
- [ ] Application Protocol Internet
- [ ] Advanced Programming Instruction

> Une **API** (Application Programming Interface) est un contrat qui permet à deux logiciels de communiquer.

---
type: single
timer: 20
difficulty: medium
tags: [api]
---

## Quel code de statut HTTP signifie « Ressource introuvable » ?

- [ ] 200
- [ ] 301
- [ ] 403
- [x] 404

> **404 Not Found** : le serveur ne trouve pas la ressource demandée. 200 = OK, 301 = redirection permanente,
> 403 = accès interdit.

---
type: single
timer: 20
difficulty: medium
tags: [api]
---

## Dans une API REST, quelle méthode HTTP sert à créer une nouvelle ressource ?

- [ ] `GET`
- [x] `POST`
- [ ] `HEAD`
- [ ] `DELETE`

> `POST` crée une ressource, `GET` la lit, `PUT`/`PATCH` la modifient et `DELETE` la supprime.

---
type: single
timer: 20
difficulty: easy
tags: [bdd]
---

## Quel langage sert à interroger une base de données relationnelle ?

- [x] SQL
- [ ] HTML
- [ ] YAML
- [ ] CSS

> **SQL** (Structured Query Language) : `SELECT`, `INSERT`, `UPDATE`, `DELETE`… sur PostgreSQL, MySQL, SQLite.

---
type: single
timer: 20
difficulty: medium
tags: [bdd]
---

## À quoi sert une clé primaire dans une table ?

- [ ] À chiffrer les données sensibles de la table
- [x] À identifier chaque ligne de la table de façon unique
- [ ] À trier les lignes de la table automatiquement
- [ ] À relier la table à une autre base de données

> La **clé primaire** identifie chaque ligne de manière unique (souvent un `id`). Une **clé étrangère** référence la
> clé primaire d'une autre table.

---
type: multiple
timer: 30
difficulty: medium
tags: [bdd]
---

## Lesquelles sont des bases de données NoSQL ? (sélectionnez 2)

- [x] MongoDB
- [ ] PostgreSQL
- [x] Redis
- [ ] MySQL

> **MongoDB** (documents) et **Redis** (clé-valeur) sont NoSQL. PostgreSQL et MySQL sont des bases relationnelles SQL.

---
type: single
timer: 20
difficulty: medium
tags: [docker]
---

## Quelle est la relation entre une image et un conteneur Docker ?

- [x] Un conteneur est une instance qui s'exécute à partir d'une image
- [ ] Une image est une instance qui s'exécute à partir d'un conteneur
- [ ] Une image et un conteneur sont deux noms pour la même chose
- [ ] Un conteneur est la version compressée et archivée d'une image

> L'**image** est un modèle figé (système de fichiers + config). Le **conteneur** en est une instance qui tourne :
> on peut lancer plusieurs conteneurs depuis la même image.

---
type: single
timer: 20
difficulty: easy
tags: [docker]
---

## Quel fichier décrit les étapes de construction d'une image Docker ?

- [ ] `compose.yaml`
- [x] `Dockerfile`
- [ ] `.dockerignore`
- [ ] `package.json`

> Le **Dockerfile** (`FROM`, `COPY`, `RUN`, `CMD`…) construit l'image. `compose.yaml` orchestre plusieurs conteneurs.

---
type: single
timer: 25
difficulty: hard
tags: [docker]
---

## Pourquoi un conteneur est-il plus léger qu'une machine virtuelle ?

- [ ] Il n'a pas besoin de système de fichiers
- [x] Il partage le noyau du système hôte
- [ ] Il ne tourne que dans le cloud
- [ ] Il compresse la mémoire vive

> Une VM embarque un système d'exploitation complet. Un conteneur partage le **noyau** de l'hôte et isole seulement
> ses processus : il démarre en quelques secondes et pèse quelques Mo.

---
type: single
timer: 20
difficulty: easy
tags: [scraping]
---

## Qu'est-ce que le web scraping ?

- [ ] Supprimer automatiquement les pages inutiles d'un site
- [x] Extraire automatiquement des données de pages web
- [ ] Optimiser le référencement d'un site dans Google
- [ ] Protéger un site contre les robots malveillants

> Le **scraping** télécharge des pages et en extrait des données (prix, articles…) avec des outils comme
> BeautifulSoup, Playwright ou Scrapy. Quand une API existe, elle est plus fiable.

---
type: single
timer: 20
difficulty: medium
tags: [scraping]
---

## Quel fichier indique aux robots les pages d'un site qu'ils peuvent explorer ?

- [x] `robots.txt`
- [ ] `sitemap.xml`
- [ ] `humans.txt`
- [ ] `.htaccess`

> `robots.txt`, à la racine du site, liste ce que les robots peuvent explorer. Un scraper respectueux le lit,
> limite son rythme et respecte les conditions d'utilisation.

---
type: multiple
timer: 30
difficulty: easy
tags: [no-code]
---

## Lesquels sont des outils d'automatisation no-code / low-code ? (sélectionnez 3)

- [x] n8n
- [x] Zapier
- [x] Make
- [ ] Kubernetes

> **n8n**, **Zapier** et **Make** relient des services par des workflows visuels. Kubernetes orchestre des conteneurs.

---
type: single
timer: 20
difficulty: medium
tags: [no-code]
---

## Quelle est la principale limite d'un outil no-code ?

- [ ] L'obligation d'écrire du code compilé
- [ ] L'impossibilité d'appeler une API externe
- [x] La dépendance à la plateforme et à ses limites
- [ ] L'absence totale d'interface graphique

> Le no-code va vite, mais on dépend de la plateforme (prix, fonctionnalités, export) : c'est le **vendor lock-in**.
> Les outils low-code permettent d'ajouter du code quand on atteint les limites.

---
type: single
timer: 20
difficulty: medium
tags: [formats]
---

## Lequel de ces textes est un JSON valide ?

- [x] `{"nom": "Ada", "age": 36}`
- [ ] `{nom: "Ada", age: 36}`
- [ ] `{"nom": "Ada", "age": 36,}`
- [ ] `{'nom': 'Ada', 'age': 36}`

> En JSON, les clés sont entre **guillemets doubles**, les chaînes aussi, et la virgule finale est interdite.

---
type: single
timer: 20
difficulty: easy
tags: [formats]
---

## En YAML, qu'est-ce qui définit l'imbrication des données ?

- [ ] Les accolades
- [x] L'indentation
- [ ] Les points-virgules
- [ ] Les balises fermantes

> YAML structure les données par **indentation** (avec des espaces, jamais de tabulations). C'est le format des
> fichiers de CI, de Docker Compose ou de Kubernetes.

---
type: single
timer: 20
difficulty: easy
tags: [formats]
---

## En Markdown, comment écrit-on un titre de niveau 2 ?

- [x] `## Titre`
- [ ] `**Titre**`
- [ ] `-- Titre`
- [ ] `> Titre`

> `#` = titre de niveau 1, `##` = niveau 2… `**texte**` met en gras et `>` crée une citation. Ce quiz est d'ailleurs
> écrit en Markdown !

---
type: single
timer: 20
difficulty: easy
tags: [terminal]
---

## Quelle commande affiche le chemin du dossier courant ?

- [ ] `ls`
- [ ] `cd`
- [x] `pwd`
- [ ] `cat`

> `pwd` (print working directory) affiche le dossier courant, `ls` liste son contenu, `cd` change de dossier et
> `cat` affiche un fichier.

---
type: single
timer: 20
difficulty: medium
tags: [terminal]
---

## Quelle commande liste aussi les fichiers cachés d'un dossier ?

- [x] `ls -a`
- [ ] `ls -l`
- [ ] `ls -h`
- [ ] `ls -r`

> `-a` (all) affiche les fichiers cachés, ceux qui commencent par un point comme `.env` ou `.gitignore`.
> `-l` donne le format long, `-h` des tailles lisibles, `-r` inverse l'ordre.

---
type: single
timer: 20
difficulty: easy
tags: [bash]
---

## Dans un shell, que fait le caractère `|` (pipe) ?

- [x] Il envoie la sortie d'une commande à la commande suivante
- [ ] Il lance les deux commandes en parallèle et en arrière-plan
- [ ] Il écrit la sortie de la commande dans un fichier texte
- [ ] Il transforme le reste de la ligne en commentaire

> Le **pipe** chaîne les commandes : `cat logs.txt | grep ERROR | wc -l` compte les lignes d'erreur.

---
type: single
timer: 20
difficulty: medium
tags: [bash]
---

## Quelle est la différence entre `>` et `>>` ?

- [ ] `>` ajoute à la fin du fichier, `>>` remplace son contenu
- [x] `>` remplace le contenu du fichier, `>>` ajoute à la fin
- [ ] `>` écrit dans un fichier, `>>` écrit dans le terminal
- [ ] `>` lit un fichier, `>>` écrit dans un fichier

> `echo a > f.txt` écrase le fichier, `echo b >> f.txt` ajoute une ligne à la fin.

---
type: single
timer: 20
difficulty: medium
tags: [bash]
---

## Que fait `chmod +x deploy.sh` ?

- [ ] Il supprime le script
- [x] Il rend le script exécutable
- [ ] Il exécute le script
- [ ] Il chiffre le script

> `chmod +x` ajoute le droit d'exécution. On lance ensuite le script avec `./deploy.sh` ; sa première ligne
> `#!/bin/bash` (le shebang) indique l'interpréteur.

---
type: single
timer: 20
difficulty: easy
tags: [ci-cd]
---

## Que signifie CI dans CI/CD ?

- [x] Continuous Integration
- [ ] Code Inspection
- [ ] Container Image
- [ ] Cloud Infrastructure

> **CI** = Continuous Integration (intégration continue), **CD** = Continuous Delivery / Deployment (livraison ou
> déploiement continu).

---
type: single
timer: 20
difficulty: medium
tags: [ci-cd]
---

## Quel est le rôle principal d'une pipeline d'intégration continue ?

- [ ] Écrire le code à la place des développeurs
- [x] Construire et tester le code à chaque modification
- [ ] Héberger le dépôt Git de toute l'équipe
- [ ] Remplacer la revue de code par des humains

> À chaque push ou pull request, la CI installe, construit, lance les tests et les linters : on détecte les
> régressions tout de suite, avant de fusionner.

---
type: single
timer: 20
difficulty: medium
tags: [ci-cd]
---

## Dans quel dossier d'un dépôt se trouvent les workflows GitHub Actions ?

- [ ] `.github/pipelines/`
- [x] `.github/workflows/`
- [ ] `.ci/workflows/`
- [ ] `.actions/github/`

> Chaque fichier YAML de `.github/workflows/` décrit un workflow : ses déclencheurs (`on: push`…) et ses jobs.

---
type: single
timer: 20
difficulty: easy
tags: [verification]
---

## Quel est le rôle d'un linter ?

- [x] Signaler les erreurs et mauvaises pratiques sans exécuter le code
- [ ] Compiler le code source en un exécutable optimisé
- [ ] Réduire la taille des fichiers envoyés au navigateur
- [ ] Déployer automatiquement le code en production

> Un **linter** (ESLint, Ruff, markdownlint…) analyse le code statiquement. Un **formatter** (Prettier, Black)
> uniformise sa mise en forme.

---
type: multiple
timer: 30
difficulty: medium
tags: [verification]
---

## Lesquels sont des outils de vérification du code ? (sélectionnez 3)

- [x] ESLint
- [x] Vitest
- [ ] Nginx
- [x] markdownlint

> ESLint et markdownlint sont des linters, Vitest lance des tests. Nginx est un serveur web.

---
type: single
timer: 20
difficulty: medium
tags: [verification]
---

## Que vérifie un test unitaire ?

- [x] Une petite partie du code, isolée du reste
- [ ] L'application entière dans un vrai navigateur
- [ ] La tenue de l'application sous une forte charge
- [ ] La sécurité du réseau de l'entreprise

> Le **test unitaire** vérifie une fonction ou un module isolé. Au-dessus viennent les tests d'intégration et les
> tests end-to-end (Playwright, Cypress).

---
type: multiple
timer: 30
difficulty: medium
tags: [observabilite]
---

## Quels sont les trois piliers de l'observabilité ? (sélectionnez 3)

- [x] Les logs
- [x] Les métriques
- [ ] Les tickets
- [x] Les traces

> **Logs** (événements), **métriques** (mesures chiffrées dans le temps) et **traces** (parcours d'une requête)
> permettent de comprendre l'état d'un système en production.

---
type: single
timer: 20
difficulty: easy
tags: [observabilite]
---

## Quel outil sert à afficher des métriques dans des tableaux de bord ?

- [ ] Git
- [x] Grafana
- [ ] Figma
- [ ] Postman

> **Grafana** affiche des tableaux de bord à partir de sources comme Prometheus, Loki ou une base SQL.

---
type: single
timer: 25
difficulty: hard
tags: [observabilite]
---

## À quoi sert une trace distribuée ?

- [x] À suivre une requête à travers plusieurs services
- [ ] À compter le nombre d'utilisateurs connectés
- [ ] À sauvegarder la base de données chaque nuit
- [ ] À chiffrer les échanges entre deux services

> Une **trace** relie les étapes d'une même requête (API → base → service tiers) pour trouver où elle ralentit ou
> échoue. OpenTelemetry est le standard ouvert pour la produire.

---
type: single
timer: 20
difficulty: easy
tags: [cloud]
---

## Gmail est un exemple de quel modèle de service cloud ?

- [ ] IaaS
- [ ] PaaS
- [x] SaaS
- [ ] FaaS

> **SaaS** : un logiciel prêt à l'emploi. **PaaS** : une plateforme pour déployer son code (Vercel, Heroku).
> **IaaS** : des serveurs et du réseau à la demande (EC2, Compute Engine).

---
type: single
timer: 20
difficulty: medium
tags: [cloud]
---

## Que signifie « serverless » ?

- [ ] Le code tourne sans aucun serveur physique
- [x] Le fournisseur gère les serveurs et facture à l'usage
- [ ] Le code tourne uniquement dans le navigateur
- [ ] Le site fonctionne sans connexion à Internet

> Il y a bien des serveurs, mais on ne les gère pas : le fournisseur lance le code à la demande et facture
> l'exécution (AWS Lambda, Cloudflare Workers, Supabase Edge Functions).

---
type: single
timer: 20
difficulty: easy
tags: [cloud]
---

## Pourquoi séparer les environnements de dev, de staging et de production ?

- [ ] Pour réduire la facture du fournisseur cloud
- [x] Pour tester les changements sans toucher les vrais utilisateurs
- [ ] Parce que la loi l'impose à toutes les entreprises
- [ ] Pour que le code s'exécute plus vite en production

> Le **staging** reproduit la production : on y valide une version avant de la déployer, avec ses propres données
> et ses propres secrets (variables d'environnement).

---
type: single
timer: 20
difficulty: easy
tags: [html]
---

## Que signifie HTML ?

- [ ] HyperTransfer Markup Language
- [x] HyperText Markup Language
- [ ] HighTech Modern Language
- [ ] HyperText Media Language

> HTML (HyperText Markup Language) est le langage de balisage standard des pages web.

---
type: single
timer: 20
difficulty: medium
tags: [html]
---

## Quelle balise HTML crée un lien cliquable vers une autre page ?

- [x] `<a>`
- [ ] `<link>`
- [ ] `<href>`
- [ ] `<url>`

> `<a href="…">` crée un lien. `<link>`, dans le `<head>`, charge une ressource comme une feuille de style.

---
type: single
timer: 20
difficulty: easy
tags: [html]
---

## Quel attribut donne un texte alternatif à une image ?

- [ ] `title`
- [x] `alt`
- [ ] `src`
- [ ] `href`

> `alt` décrit l'image pour les lecteurs d'écran et s'affiche si elle ne charge pas : il est essentiel pour
> l'accessibilité.

---
type: multiple
timer: 30
difficulty: medium
tags: [javascript]
---

## Lesquelles sont des méthodes natives des tableaux JavaScript ? (sélectionnez 3)

- [x] `map`
- [x] `filter`
- [ ] `transform`
- [x] `reduce`

> `map()`, `filter()` et `reduce()` sont des méthodes natives des tableaux. `transform()` n'existe pas.

---
type: single
timer: 15
difficulty: hard
tags: [javascript]
---

## Quelle est la complexité d'une recherche dans une `Map` JavaScript ?

- [ ] O(n)
- [ ] O(n log n)
- [x] O(1) amortie
- [ ] O(log n)

> Une `Map` repose sur une table de hachage : une recherche se fait en O(1) amorti.
