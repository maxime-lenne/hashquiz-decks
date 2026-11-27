---
title: "Survivre à l'open space tech"
description: >
  Deck grand public HashQuiz : 10 questions décalées sur le jargon, les blagues et les petits rituels
  de la vie dans une équipe tech.
theme: default
author: Maxime Lenne
tags: [humour, jargon, bureau, dev, grand-public]
solo: true
---

---
type: single
timer: 20
difficulty: easy
tags: [web, http]
---

## Sur le web, que signifie une erreur 404 ?

- [x] La page est introuvable
- [ ] Le serveur est en panne
- [ ] L'accès est interdit
- [ ] La connexion est trop lente

> **404 Not Found** : le serveur répond bien, mais la page demandée n'existe pas (ou plus). Une panne côté serveur
> donne plutôt une erreur 500, un accès refusé une 403.

---
type: multiple
timer: 30
difficulty: medium
tags: [web, http]
---

## Lesquels sont de vrais codes HTTP ? (sélectionnez 3)

- [x] 200 OK
- [x] 404 Not Found
- [x] 418 I'm a teapot
- [ ] 299 Coffee Break

> **418 I'm a teapot** vient d'un poisson d'avril de 1998 (RFC 2324) : une théière qui refuse de faire du café. Il est
> toujours réservé dans la norme HTTP ! **299 Coffee Break**, lui, n'existe pas.

---
type: single
timer: 20
difficulty: easy
tags: [debug, humour]
---

## En quoi consiste le « rubber duck debugging » ?

- [x] Expliquer son code à voix haute à un canard en plastique
- [ ] Lancer ses tests dans son bain
- [ ] Faire relire son code par un stagiaire
- [ ] Supprimer le code jusqu'à ce que le bug disparaisse

> En expliquant son code ligne par ligne à un **canard en plastique**, on trouve souvent le bug tout seul. La méthode
> vient du livre The Pragmatic Programmer (1999).

---
type: single
timer: 20
difficulty: medium
tags: [support, jargon]
---

## Que signifie PEBKAC, le diagnostic préféré du support informatique ?

- [x] Le problème se situe entre la chaise et le clavier
- [ ] Le câble réseau est débranché
- [ ] Le PC a besoin d'être redémarré
- [ ] Le pilote de l'imprimante est trop vieux

> **PEBKAC** = « Problem Exists Between Keyboard And Chair ». Autrement dit : c'est l'utilisateur. Un classique, avec
> son cousin « erreur ID-10-T ».

---
type: single
timer: 20
difficulty: medium
tags: [vim, terminal]
---

## Dans l'éditeur Vim, quelle commande permet de quitter sans enregistrer ?

- [x] :q!
- [ ] Ctrl+C
- [ ] exit
- [ ] Alt+F4

> Taper **Échap** puis **`:q!`**. Sur Stack Overflow, la question « How do I exit Vim? » a été vue plus de 2 millions
> de fois.

---
type: single
timer: 20
difficulty: easy
tags: [securite, mot-de-passe]
---

## Quel est, année après année, l'un des mots de passe les plus utilisés au monde ?

- [x] 123456
- [ ] azerty2000
- [ ] MotDePasse!
- [ ] 0000

> **123456** truste le haut des classements des mots de passe les plus fuités, avec « password » et « qwerty ». Il se
> casse en moins d'une seconde : vive le gestionnaire de mots de passe.

---
type: single
timer: 20
difficulty: easy
tags: [agile, scrum]
---

## Selon le guide Scrum, combien de temps doit durer le daily (la réunion quotidienne) au maximum ?

- [x] 15 minutes
- [ ] 5 minutes
- [ ] 30 minutes
- [ ] 1 heure, café compris

> Le **Daily Scrum** est limité à **15 minutes**. On le fait souvent debout (« stand-up ») pour s'assurer qu'il ne
> s'éternise pas.

---
type: single
timer: 20
difficulty: easy
tags: [docker, humour]
---

## Quel outil est souvent présenté comme la réponse au fameux « ça marche sur ma machine » ?

- [x] Docker
- [ ] Excel
- [ ] Slack
- [ ] PowerPoint

> **Docker** emballe une application avec tout son environnement dans un conteneur, qui tourne de la même façon sur le
> poste du dev, en test et en production. La blague dit qu'on a fini par livrer la machine du dev.

---
type: single
timer: 20
difficulty: easy
tags: [deploiement, humour]
---

## Pourquoi évite-t-on traditionnellement de mettre en production le vendredi après-midi ?

- [x] Pour ne pas passer son week-end à réparer un incident
- [ ] Parce que les serveurs sont moins puissants le vendredi
- [ ] Parce que c'est interdit par la loi
- [ ] Parce qu'internet est plus lent le week-end

> Si une mise en production casse quelque chose vendredi à 17 h, l'équipe risque d'y passer le week-end. D'où le
> dicton « Don't deploy on Friday ».

---
type: single
timer: 20
difficulty: medium
tags: [binaire, humour]
---

## « Il y a 10 sortes de personnes : celles qui comprennent le binaire et les autres. » Combien vaut 10 en binaire ?

- [x] 2
- [ ] 10
- [ ] 1
- [ ] 8

> En binaire, **10** vaut **2** : 1 × 2 + 0 × 1. La blague compte donc bien deux sortes de personnes.
