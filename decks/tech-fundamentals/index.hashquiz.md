---
title: Fondamentaux tech
description: >
  Deck d'exemple HashQuiz : 2 à 3 questions sur chaque base de la tech,
  du terminal au cloud. Terminal, bash, Git, JSON / YAML / Markdown,
  HTML, API, bases de données, Docker, CI/CD, outils de vérification,
  observabilité, cloud, scraping et no-code.
theme: default
author: Maxime Lenne
tags: [tech, fondamentaux, git, api, bdd, docker, ci-cd, cloud]
solo: true
---

---
type: single
timer: 20
difficulty: easy
tags: [terminal]
---

## Quelle commande affiche le chemin du dossier courant dans un terminal ?

- [ ] `ls`
- [x] `pwd`
- [ ] `cd`
- [ ] `cat`

> `pwd` (*print working directory*) affiche le dossier courant. `ls` liste son contenu, `cd` change de dossier et `cat`
> affiche le contenu d'un fichier.

---
type: single
timer: 20
difficulty: medium
tags: [terminal]
---

## Quel raccourci interrompt la commande en cours d'exécution dans le terminal ?

- [ ] `Ctrl+Z`
- [ ] `Ctrl+D`
- [x] `Ctrl+C`
- [ ] `Ctrl+L`

> `Ctrl+C` envoie le signal d'interruption (SIGINT) au programme. `Ctrl+Z` le suspend, `Ctrl+D` signale la fin de
> l'entrée (et ferme le shell) et `Ctrl+L` efface l'écran.

---
type: single
timer: 20
difficulty: medium
tags: [terminal, vim]
---

## Dans l'éditeur Vim, quelle commande permet de quitter sans enregistrer ?

- [x] `:q!`
- [ ] `Ctrl+C`
- [ ] `exit`
- [ ] `Alt+F4`

> Taper `Échap` puis `:q!`. `:wq` enregistre puis quitte. Sur Stack Overflow, la question « How do I exit Vim? » a été
> vue plus de 2 millions de fois.

---
type: single
timer: 20
difficulty: easy
tags: [bash]
---

## Que fait la commande `ls | grep log` ?

- [x] Elle filtre la liste des fichiers pour garder ceux qui contiennent « log »
- [ ] Elle crée un fichier nommé « log » à partir de la liste des fichiers
- [ ] Elle exécute `ls` puis `grep` l'un après l'autre, sans lien entre eux
- [ ] Elle enregistre la liste des fichiers dans le fichier « log »

> Le **pipe** `|` envoie la sortie d'une commande en entrée de la suivante. Enchaîner de petites commandes
> spécialisées est le cœur de la philosophie Unix.

---
type: single
timer: 20
difficulty: medium
tags: [bash]
---

## Quelle est la différence entre `echo ok > out.txt` et `echo ok >> out.txt` ?

- [x] `>` remplace le contenu du fichier, `>>` ajoute à la fin
- [ ] `>` ajoute à la fin du fichier, `>>` remplace le contenu
- [ ] `>` redirige les erreurs, `>>` redirige la sortie standard
- [ ] `>` écrit dans un fichier, `>>` écrit dans un dossier

> `>` crée ou **écrase** le fichier, `>>` **ajoute** à la fin. Les erreurs (sortie d'erreur) se redirigent avec
> `2>`.

---
type: single
timer: 20
difficulty: easy
tags: [git]
---

## Quelle commande enregistre les modifications indexées dans l'historique local du dépôt ?

- [ ] `git push`
- [x] `git commit`
- [ ] `git add`
- [ ] `git merge`

> `git add` indexe les modifications, `git commit` les enregistre dans l'historique **local**, puis `git push` les
> envoie vers le dépôt distant (GitHub, GitLab...).

---
type: single
timer: 20
difficulty: medium
tags: [git]
---

## Que fait `git pull` ?

- [x] Un `git fetch` suivi d'un `git merge` (ou d'un rebase)
- [ ] Un `git push` suivi d'un `git fetch`
- [ ] Un `git clone` suivi d'un `git checkout`
- [ ] Un `git stash` suivi d'un `git reset`

> `git pull` récupère les commits du dépôt distant (`fetch`) puis les intègre à la branche courante (`merge` par
> défaut, ou `rebase` avec `--rebase`).

---
type: single
timer: 20
difficulty: easy
tags: [git]
---

## À quoi sert une Pull Request (ou Merge Request) ?

- [x] À proposer la fusion d'une branche, avec relecture et vérifications
- [ ] À télécharger la dernière version d'un dépôt distant
- [ ] À annuler le dernier commit d'une branche partagée
- [ ] À créer une copie privée d'un dépôt sur son compte

> Une Pull Request demande de fusionner une branche dans une autre. C'est le lieu de la **revue de code** et des
> vérifications automatiques (CI) avant la fusion. Une copie d'un dépôt sur son compte est un *fork*.

---
type: single
timer: 30
difficulty: medium
tags: [formats, json]
---

## Lequel de ces objets est du JSON valide ?

- [x] `{"nom": "Ada", "age": 36}`
- [ ] `{nom: "Ada", age: 36}`
- [ ] `{'nom': 'Ada', 'age': 36}`
- [ ] `{"nom": "Ada", "age": 36,}`

> En JSON, les clés et les chaînes sont entre **guillemets doubles**, et la virgule finale est interdite. Les autres
> écritures sont valides en JavaScript, pas en JSON.

---
type: single
timer: 20
difficulty: easy
tags: [formats, yaml]
---

## En YAML, qu'est-ce qui indique qu'une clé est imbriquée dans une autre ?

- [x] L'indentation avec des espaces
- [ ] Les accolades autour du bloc
- [ ] Les balises ouvrantes et fermantes
- [ ] Le point-virgule en fin de ligne

> YAML structure les données par l'**indentation** (des espaces, jamais de tabulations). Il est très utilisé pour la
> configuration : CI/CD, Docker Compose, Kubernetes, frontmatter des fichiers Markdown...

---
type: single
timer: 20
difficulty: easy
tags: [formats, markdown]
---

## Quelle syntaxe Markdown produit un titre de niveau 2 ?

- [x] `## Titre`
- [ ] `**Titre**`
- [ ] `> Titre`
- [ ] `- Titre`

> En Markdown, le nombre de `#` donne le niveau du titre. `**...**` met en gras, `>` crée une citation et `-` un
> élément de liste. Ce quiz est d'ailleurs écrit en Markdown.

---
type: single
timer: 20
difficulty: easy
tags: [html]
---

## Que signifie HTML ?

- [ ] Hyper Transfer Markup Language
- [x] HyperText Markup Language
- [ ] High-Tech Modern Language
- [ ] HyperText Media Language

> HTML (*HyperText Markup Language*) est le langage de balisage qui décrit la structure des pages web. Le CSS gère
> leur apparence et le JavaScript leur comportement.

---
type: single
timer: 20
difficulty: medium
tags: [html]
---

## Quelle balise HTML crée un lien vers une autre page ?

- [x] `<a>`
- [ ] `<link>`
- [ ] `<href>`
- [ ] `<url>`

> `<a href="...">` crée un lien cliquable. `<link>` relie la page à une ressource (une feuille CSS par exemple) et
> `href` est un attribut, pas une balise.

---
type: single
timer: 20
difficulty: easy
tags: [api, http]
---

## Quelle méthode HTTP utilise-t-on en général pour créer une ressource dans une API REST ?

- [ ] `GET`
- [x] `POST`
- [ ] `DELETE`
- [ ] `HEAD`

> Par convention REST : `GET` lit, `POST` crée, `PUT` / `PATCH` modifient et `DELETE` supprime.

---
type: single
timer: 20
difficulty: easy
tags: [api, http]
---

## Quel code de statut HTTP signifie « ressource introuvable » ?

- [ ] `200`
- [ ] `301`
- [ ] `403`
- [x] `404`

> Les codes `2xx` indiquent un succès, `3xx` une redirection, `4xx` une erreur du client (`403` : accès interdit,
> `404` : introuvable) et `5xx` une erreur du serveur.

---
type: single
timer: 20
difficulty: medium
tags: [api, http]
---

## Que signifie une réponse `401 Unauthorized` d'une API ?

- [x] La requête n'est pas authentifiée : clé ou jeton absent ou invalide
- [ ] La ressource a été déplacée de façon permanente à une autre adresse
- [ ] Le serveur a rencontré une erreur interne en traitant la requête
- [ ] La requête a réussi mais la réponse ne contient aucun contenu

> `401` signifie que le client ne s'est pas (ou mal) **authentifié**. Si le client est identifié mais n'a pas les
> droits, l'API répond `403 Forbidden`.

---
type: single
timer: 20
difficulty: easy
tags: [bdd, sql]
---

## Quel langage sert à interroger une base de données relationnelle ?

- [x] SQL
- [ ] HTML
- [ ] CSS
- [ ] YAML

> SQL (*Structured Query Language*) permet de lire et modifier les données (`SELECT`, `INSERT`, `UPDATE`, `DELETE`)
> des bases relationnelles comme PostgreSQL, MySQL ou SQLite.

---
type: single
timer: 20
difficulty: medium
tags: [bdd]
---

## À quoi sert la clé primaire d'une table ?

- [x] À identifier chaque ligne de la table de façon unique
- [ ] À chiffrer les données sensibles de la table
- [ ] À accélérer les sauvegardes de la base de données
- [ ] À autoriser l'accès à la table depuis une API

> La clé primaire (souvent une colonne `id`) identifie chaque ligne de façon **unique**. Les clés étrangères des
> autres tables la référencent pour créer des relations.

---
type: multiple
timer: 30
difficulty: medium
tags: [bdd, nosql]
---

## Lesquelles de ces bases de données sont des bases NoSQL ? (sélectionnez 2)

- [x] MongoDB
- [x] Redis
- [ ] PostgreSQL
- [ ] MySQL

> **MongoDB** (documents JSON) et **Redis** (clé-valeur en mémoire) sont des bases NoSQL. PostgreSQL et MySQL sont
> des bases relationnelles interrogées en SQL.

---
type: single
timer: 20
difficulty: easy
tags: [docker]
---

## Quelle est la relation entre une image et un conteneur Docker ?

- [x] Le conteneur est une instance en exécution d'une image
- [ ] L'image est une instance en exécution d'un conteneur
- [ ] L'image et le conteneur sont deux noms de la même chose
- [ ] Le conteneur est le fichier qui décrit comment construire l'image

> Une **image** est un modèle figé (construit à partir d'un `Dockerfile`). Un **conteneur** est une instance de cette
> image qui s'exécute, de façon isolée : on peut en lancer plusieurs à partir de la même image.

---
type: single
timer: 20
difficulty: medium
tags: [docker]
---

## Quel outil lance une application et sa base de données en plusieurs conteneurs à partir d'un seul fichier YAML ?

- [x] Docker Compose
- [ ] Docker Hub
- [ ] Docker Desktop
- [ ] Docker Scout

> **Docker Compose** décrit plusieurs services (app, base de données, cache...) dans un `compose.yaml` et les lance
> ensemble avec `docker compose up`. Docker Hub est le registre public d'images.

---
type: single
timer: 20
difficulty: easy
tags: [ci-cd]
---

## Que signifie CI/CD ?

- [x] Continuous Integration / Continuous Delivery (ou Deployment)
- [ ] Code Inspection / Code Delivery
- [ ] Container Integration / Cloud Deployment
- [ ] Continuous Inspection / Continuous Debugging

> La **CI** construit et teste le code à chaque modification. La **CD** livre ou déploie automatiquement ce qui a
> passé la CI. Le but : des livraisons fréquentes, petites et fiables.

---
type: single
timer: 20
difficulty: medium
tags: [ci-cd, github]
---

## Où se définissent les workflows GitHub Actions d'un dépôt ?

- [x] `.github/workflows/*.yml`
- [ ] `.git/hooks/*.sh`
- [ ] `package.json`
- [ ] `.gitlab-ci.yml`

> GitHub Actions lit les fichiers YAML de `.github/workflows/`. Chaque workflow se déclenche sur un événement (push,
> pull request, planning...). `.gitlab-ci.yml` est l'équivalent chez GitLab.

---
type: single
timer: 20
difficulty: easy
tags: [verification]
---

## Que fait un linter (ESLint, Ruff, markdownlint...) ?

- [x] Il analyse le code sans l'exécuter pour signaler erreurs et écarts de style
- [ ] Il compile le code source en un binaire optimisé pour la production
- [ ] Il exécute le code en production et redémarre l'application en cas d'erreur
- [ ] Il chiffre le code source pour le protéger avant de le publier

> Un linter fait de l'**analyse statique** : il repère bugs probables et écarts aux conventions avant l'exécution.
> Avec les tests et la vérification des types, il fait partie des contrôles lancés en CI ou avant chaque commit.

---
type: multiple
timer: 30
difficulty: medium
tags: [verification, tests]
---

## Lesquelles de ces pratiques vérifient automatiquement le code avant sa fusion ? (sélectionnez 3)

- [x] Les tests automatisés
- [x] La vérification des types
- [x] Le lint du code
- [ ] Le déploiement en production

> Tests, vérification des types (TypeScript, mypy...) et lint tournent en CI sur chaque pull request. Le
> déploiement en production vient **après** ces vérifications.

---
type: multiple
timer: 30
difficulty: easy
tags: [observabilite]
---

## Quels sont les 3 piliers de l'observabilité ? (sélectionnez 3)

- [x] Les logs
- [x] Les métriques
- [x] Les traces
- [ ] Les sauvegardes

> Les **logs** racontent les événements, les **métriques** mesurent l'état dans le temps (CPU, latence, erreurs) et
> les **traces** suivent une requête à travers les services. Ensemble, ils aident à comprendre un incident.

---
type: single
timer: 20
difficulty: medium
tags: [observabilite]
---

## Quel outil collecte des métriques et est souvent affiché dans des tableaux de bord Grafana ?

- [x] Prometheus
- [ ] Terraform
- [ ] Jenkins
- [ ] Ansible

> **Prometheus** collecte et stocke des métriques horodatées, que **Grafana** affiche en tableaux de bord et alertes.
> Terraform et Ansible gèrent l'infrastructure, Jenkins fait de la CI/CD.

---
type: single
timer: 20
difficulty: easy
tags: [cloud]
---

## Une messagerie web comme Gmail est un exemple de quel modèle de cloud ?

- [x] SaaS
- [ ] IaaS
- [ ] PaaS
- [ ] CaaS

> **SaaS** : un logiciel prêt à l'emploi. **PaaS** : une plateforme où déployer son code (Vercel, Heroku). **IaaS** :
> des machines et réseaux à gérer soi-même (EC2, Compute Engine).

---
type: single
timer: 20
difficulty: medium
tags: [cloud, config]
---

## Qu'est-ce qu'une variable d'environnement ?

- [x] Une valeur de configuration lue par le programme au lancement, hors du code
- [ ] Une variable globale déclarée en haut du code source du programme
- [ ] Une région du fournisseur cloud où l'application est déployée
- [ ] Un fichier de logs généré par le serveur au démarrage

> Les variables d'environnement (`DATABASE_URL`, clés d'API...) changent d'un environnement à l'autre sans toucher
> au code. Les secrets s'y placent : on ne les commite jamais (`.env` va dans `.gitignore`).

---
type: single
timer: 20
difficulty: easy
tags: [cloud]
---

## À quoi sert un environnement de staging (préproduction) ?

- [x] À tester une version dans des conditions proches de la production
- [ ] À stocker les sauvegardes quotidiennes de la base de production
- [ ] À héberger le code source et l'historique des versions du projet
- [ ] À servir les utilisateurs quand la production est en panne

> Le **staging** reproduit la production (configuration, données de test réalistes) pour valider une version avant
> de la livrer. Le chemin classique : développement, staging, production.

---
type: single
timer: 20
difficulty: easy
tags: [scraping]
---

## Qu'est-ce que le web scraping ?

- [x] Extraire automatiquement des données de pages web
- [ ] Supprimer les cookies et les traceurs d'un navigateur
- [ ] Optimiser un site pour les moteurs de recherche
- [ ] Compresser les images d'un site pour l'accélérer

> Un *scraper* télécharge des pages et en extrait des données (prix, articles, annonces...). Quand une **API**
> existe, elle est plus fiable : le scraping casse dès que la page change.

---
type: single
timer: 20
difficulty: medium
tags: [scraping]
---

## Quel fichier d'un site indique aux robots les pages qu'ils ne doivent pas parcourir ?

- [x] `robots.txt`
- [ ] `sitemap.xml`
- [ ] `.htaccess`
- [ ] `manifest.json`

> `robots.txt`, à la racine du site, liste les règles pour les robots. Un scraper respectueux le lit, limite son
> rythme de requêtes et vérifie les conditions d'utilisation et le RGPD.

---
type: single
timer: 20
difficulty: easy
tags: [no-code]
---

## Qu'est-ce qu'un outil no-code ?

- [x] Un outil pour créer applications ou automatisations sans écrire de code
- [ ] Un langage de programmation qui n'utilise aucun mot-clé réservé
- [ ] Un éditeur de code qui supprime automatiquement le code inutilisé
- [ ] Un framework web qui fonctionne sans aucune dépendance externe

> Le no-code remplace le code par une interface visuelle (blocs, formulaires, glisser-déposer). Le **low-code** ajoute
> la possibilité d'écrire un peu de code quand l'interface ne suffit pas.

---
type: multiple
timer: 30
difficulty: medium
tags: [no-code, automatisation]
---

## Lesquels de ces outils automatisent des tâches entre applications sans coder ? (sélectionnez 3)

- [x] n8n
- [x] Zapier
- [x] Make
- [ ] Kubernetes

> **n8n**, **Zapier** et **Make** relient des applications par des workflows visuels (un déclencheur, puis des
> actions). Kubernetes orchestre des conteneurs : c'est un outil d'infrastructure.
