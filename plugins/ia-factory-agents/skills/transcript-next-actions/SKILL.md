---
name: transcript-next-actions
description: "Classer un transcript en Interne, Formation, Prospect ou Client, le rattacher au bon espace, synthétiser en 120 mots, garder les phrases marquantes, extraire les actions et ranger celles de l'utilisateur dans sa base Tâches. À utiliser en tâche planifiée (toutes les heures ou chaque soir) ou à la main pour traiter et ranger des transcripts de réunion."
---

# Agent Transcript to Drive/Notion + Next Actions

Fournir le transcript et Ma voix pour le ton des synthèses. Déduire le rangement de la structure existante ou demander la destination. Les Règles IA de l’utilisateur, déjà dans les instructions personnalisées de son IA, restent applicables.

## Utilisation dans Codex

Utiliser les fichiers fournis et les connecteurs disponibles dans le périmètre demandé. Les documents « Ma voix » et « ADN, méthode & économie » sont ceux de l’utilisateur, pas des fichiers livrés avec le plugin. Demander les informations indispensables manquantes ; les noms de fichiers indiqués sont des exemples.

**Où trouver ses documents de référence** (ADN, méthode & économie ; Ma voix) : dans son Notion (page « Mes documents de référence » du Hub Freelance) ou dans son Google Drive (dossier « Mes documents de référence »), via le connecteur. Ses Règles IA, dans les instructions de son IA, indiquent lequel. Introuvables : les lui demander, ne jamais deviner.

Pour une mise à jour Notion ou Drive demandée, identifier la destination et lire son schéma réel avant d’écrire. Vérifier les entrées existantes pour éviter les doublons et préserver le contenu sans rapport. Sans accès, fournir le contenu prêt à intégrer et préciser ce qui n’a pas été enregistré. Le skill propose de créer la tâche planifiée ChatGPT et ne la crée que sur un oui explicite. Préparer les messages en brouillon ; les envoyer ou publier uniquement sur demande explicite. Le choix d’un skill ne lance pas les autres automatiquement.

Agir comme assistant de suivi post-réunion, **premier maillon de toute la chaîne d'agents**. Premier job : **classer chaque transcript et le rattacher au BON endroit** (un dossier si l'utilisateur travaille en fichiers, une fiche et des relations sur Notion). Un transcript bien rattaché nourrit le bon agent en aval ; mal classé, il pollue tout.

## Avant de commencer : rassembler les sources

1. Récupérer le transcript : texte collé, fichier, ou via connecteur (Notion, Fireflies…). Si seul un **ID de transcript** est fourni (cas webhook), aller chercher le texte complet via le connecteur avant de traiter.
2. Chercher **Ma voix** pour le ton des synthèses.
3. Identifier la structure de rangement : base Notion « Transcripts de réunion » + bases Prospects/Clients, Projets, Tâches (IDs, colonnes). Des bases de données, pas des pages dans des pages. Si l'utilisateur ne l'a pas décrite et qu'elle ne se déduit pas de la base, la demander une fois (à la main uniquement).
4. Lire ses préférences d'actions s'il les a données : quel niveau de détail, quelles actions il veut voir sortir. Une idée lancée en l'air ne devient pas une tâche.

## En tâche planifiée

C'est le mode normal : **toutes les heures ou chaque soir**, selon le nombre de rendez-vous.
- Traiter **uniquement les nouveaux transcripts** : ceux dont la case **Traité** n'est pas cochée (ou dont le Transcript ID n'a pas encore de fiche). Cocher Traité à la fin de chaque transcript.
- **Aucune question** : ce qui est incertain est marqué `[À VALIDER]` dans la fiche, et listé en fin de compte-rendu de la tâche.
- Rien de nouveau : le dire en une ligne et s'arrêter.

À la fin de la première utilisation, rappeler que l'agent est fait pour tourner en tâche planifiée et **proposer de créer la tâche maintenant** (toutes les heures ou chaque soir, selon le nombre de rendez-vous), puis la créer sur un oui. Si une tâche Transcript existe déjà, ne pas en créer une deuxième. Prompt de la tâche, adapté à son outil de prise de notes et à sa structure :

> « Lance $transcript-next-actions en tâche planifiée : traite les nouveaux transcripts de [Fathom / Fireflies / ma base Notion X] non cochés Traité, range chaque fiche au bon endroit, mets mes actions dans ma base Tâches. Ne me pose pas de questions. »

## Qui fait quoi : Transcript, Voix du client, Chef de projet

- **Cet agent (Transcript)** est l'assistante administrative, appel par appel : il range, résume ce qui s'est dit, sort les actions et garde 2 à 3 phrases marquantes. Il n'analyse pas au-delà de l'appel.
- **L'agent Voix du client** est l'analyste marketing, sur tous les appels prospects et clients à la fois : il repère ce qui revient d'un appel à l'autre, le confronte à l'ADN et propose. Il part des phrases marquantes pour s'orienter : elles ne font pas doublon avec lui, elles sont son point d'entrée. Les garder même quand l'agent Voix du client est installé.
- **L'agent Chef de projet** rédige le récap à envoyer au client. Cet agent n'en écrit pas : sa synthèse reste interne.
- Pas de base de verbatims à part : tout reste dans la fiche transcript, avec le transcript complet.

## Étape 1 : identifier le type d'appel (bloquante)

Toujours commencer par classer dans l'une des **4 familles**. Aucune synthèse avant.

- 🧩 **Interne** : équipe, freelances, orga, brainstorm, perso → espace/projet interne → décisions, qui fait quoi.
- 🎓 **Formation** : suivie ou donnée, webinaire, atelier → base Ressources/Notes → apprentissages, idées à appliquer.
- 🎯 **Prospect** : découverte, R1, suivi de vente → base Prospects/Clients → qualification, douleurs, objections, next step.
- 🤝 **Client** : delivery, atelier, suivi de mission → fiche Projet → avancement, jalons, décisions, blocages, satisfaction.

Type ambigu → hypothèse marquée `[À VALIDER]`. Le champ Type est toujours l'une de ces 4 valeurs.

## Étape 2 : rattacher

Interne → projet/sujet d'orga · Formation → thématique · Prospect → opportunité du pipeline · Client → client + projet. La fiche existe → **rattacher** (relation). Elle n'existe pas → **créer l'entrée** dans la bonne base avant de rattacher. Hésitation → `[À VALIDER]`.

## Étape 3 : synthétiser (court, à l'angle du type)

**5 à 8 puces, ~120 mots max.** Rapporter ce qui s'est dit dans cet appel, sans interpréter au-delà : les récurrences entre appels, c'est l'agent Voix du client.
- Interne : décisions, arbitrages, qui porte quoi.
- Formation : 3-5 apprentissages + ce qu'il faut appliquer.
- Prospect : douleurs, qualification (urgence / budget / décideur), objections, signaux d'achat.
- Client : avancement, jalons, décisions, blocages, « dans quel camp est la balle », satisfaction.

## Étape 4 : mettre à jour la fiche

Écrire uniquement ce qui **change**, là où ça doit aller. Pas de réécriture complète.

## Étape 4 bis : garder les phrases marquantes (prospect et client)

Pour les types 🎯 Prospect et 🤝 Client : 2 à 3 phrases **mot pour mot** de la personne (une douleur, une objection, un déclic). Jamais reformulées, jamais plus de 3 : un appel ne doit pas peser plus que les autres. C'est le point d'entrée de l'agent Voix du client, à garder même quand cet agent est installé.

## Étape 5 : extraire et ranger les next actions

Séparer 🔹 **Moi** de 🔸 **l'Autre**. Chaque action : responsable + échéance (`[à caler]` si non dite) + camp de la balle.

- 🔹 **Les actions de l'utilisateur vont dans la base Tâches** (la base « Tâches » du Hub Freelance, ou sa propre base de tâches). Une ligne par action : Tâche (verbe + objet), Échéance (vide si personne ne l'a dite), Statut « À faire », Type (Acquisition / Delivery / Contenu / Admin), relations **Client / Deal**, **Projet** (mission client) et **Transcript** (la fiche de l'appel). Avant de créer, vérifier qu'une tâche identique n'existe pas déjà.
- 🔸 **Les actions de l'Autre restent dans la fiche transcript**, colonne Next actions. Elles ne vont pas dans la base Tâches : elles ne dépendent pas de l'utilisateur.
- La colonne **Next actions** de la fiche garde le récap des deux camps, une ligne par action. La base Tâches reste la seule liste de travail.
- Pas de base Tâches trouvée : écrire les actions dans la fiche et le signaler en fin de compte-rendu (« tes actions sont dans la fiche, dis-moi quelle base Tâches utiliser »). Relation Transcript ou Projet absente de la base Tâches : remplir ce qui existe et le signaler une fois. En tâche planifiée, le noter sans poser de question.

## Champs de la fiche transcript (Notion)

Réunion (titre) · Lien transcript · Transcript ID · Participants (multi-select ou Person) · Durée (min) · Type (🧩/🎓/🎯/🤝) · Client / Deal (relation) · Sujets abordés · Synthèse (≤120 mots) · Phrases marquantes (prospect et client) · Next actions (récap 🔹/🔸 ; les actions de l'utilisateur vivent dans la base Tâches) · Résumé (2-3 lignes TL;DR) · Traité (case à cocher). Le transcript complet reste accessible (dans la fiche ou par le lien). Tout en puces.

## Format de sortie

1. **Type d'appel** + **Rattachement** (fiche, `[À VALIDER]`, ou « créée »)
2. **Synthèse** (5-8 puces, ≤120 mots)
3. **MAJ de la fiche** (ce qui change)
4. **Phrases marquantes** (prospect et client)
5. **Next actions** 🔹 Moi (créées dans la base Tâches) · 🔸 Autre (dans la fiche)


## Règles (non négociables)

1. **Tri d'abord** : le type est posé AVANT de synthétiser.
2. **Zéro invention** : incertain → `[À VALIDER]` / `[à caler]`.
3. **Ma voix** : net, sans tics IA, sans tiret cadratin.
4. **Synthèse bornée** : ≤120 mots, en puces.
5. **Aucune échéance hallucinée.**
6. **Phrases marquantes mot pour mot**, ou rien.
7. **Les actions de l'utilisateur dans la base Tâches**, celles des autres dans la fiche.
8. **Pas de récap client** : c'est l'agent Chef de projet.

## Déclenchement type

En tâche planifiée, toutes les heures ou chaque soir selon le nombre de rendez-vous ; à la main sur un transcript ; avant un point projet ou hebdo pour consolider. Les tâches planifiées se déclenchent à heure fixe, pas à la fin d'un appel.

## Exemples et gabarit

Pour calibrer le rendu ou utiliser un gabarit, lire [exemples-et-template.md](references/exemples-et-template.md). Les exemples illustrent une méthode ; leurs chiffres, témoignages et dates ne sont pas des faits concernant l’utilisateur.
