---
name: transcript-next-actions
description: "Classer un transcript en Interne, Formation, Prospect ou Client, le rattacher au bon espace, synthétiser en 120 mots, garder les phrases marquantes et extraire les actions. À utiliser en tâche planifiée (toutes les heures ou chaque soir) ou à la main pour traiter et ranger des transcripts de réunion."
---

# Agent Transcript to Drive/Notion + Next Actions

Fournir le transcript et Ma voix pour le ton des synthèses. Déduire le rangement de la structure existante ou demander la destination. Les Règles IA de l’utilisateur, déjà dans les instructions personnalisées de son IA, restent applicables.

## Utilisation dans Codex

Utiliser les fichiers fournis et les connecteurs disponibles dans le périmètre demandé. Les documents « Ma voix » et « ADN, méthode & économie » sont ceux de l’utilisateur, pas des fichiers livrés avec le plugin. Demander les informations indispensables manquantes ; les noms de fichiers indiqués sont des exemples.

**Où trouver ses documents de référence** (ADN, méthode & économie ; Ma voix) : dans son Notion (page « Mes documents de référence » du Hub Freelance) ou dans son Google Drive (dossier « Mes documents de référence »), via le connecteur. Ses Règles IA, dans les instructions de son IA, indiquent lequel. Introuvables : les lui demander, ne jamais deviner.

Pour une mise à jour Notion ou Drive demandée, identifier la destination et lire son schéma réel avant d’écrire. Vérifier les entrées existantes pour éviter les doublons et préserver le contenu sans rapport. Sans accès, fournir le contenu prêt à intégrer et préciser ce qui n’a pas été enregistré. Le skill ne crée pas lui-même de tâche planifiée : il donne le prompt prêt à coller dans une tâche planifiée ChatGPT. Préparer les messages en brouillon ; les envoyer ou publier uniquement sur demande explicite. Le choix d’un skill ne lance pas les autres automatiquement.

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

À la première utilisation, rappeler que l'agent est fait pour tourner en tâche planifiée, et donner le prompt prêt à coller, adapté à son outil de prise de notes et à sa structure, par exemple :

> « Lance $transcript-next-actions en tâche planifiée : traite les nouveaux transcripts de [Fathom / Fireflies / ma base Notion X] non cochés Traité, range chaque fiche au bon endroit, sors mes next actions. Ne me pose pas de questions. »

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

**5 à 8 puces, ~120 mots max.**
- Interne : décisions, arbitrages, qui porte quoi.
- Formation : 3-5 apprentissages + ce qu'il faut appliquer.
- Prospect : douleurs, qualification (urgence / budget / décideur), objections, signaux d'achat.
- Client : avancement, jalons, décisions, blocages, « dans quel camp est la balle », satisfaction.

## Étape 4 : mettre à jour la fiche

Écrire uniquement ce qui **change**, là où ça doit aller. Pas de réécriture complète.

## Étape 4 bis : garder les phrases marquantes (prospect et client)

Pour les types 🎯 Prospect et 🤝 Client : 2 à 3 phrases **mot pour mot** de la personne (une douleur, une objection, un déclic). Jamais reformulées. C'est la matière de l'agent Voix du client.

## Étape 5 : extraire les next actions

Séparer 🔹 **Moi** de 🔸 **l'Autre**. Chaque action : responsable + échéance (`[à caler]` si non dite) + camp de la balle. Si une base **Tâches** existe, créer une entrée par action, reliée à la fiche.

## Champs de la fiche transcript (Notion)

Réunion (titre) · Lien transcript · Transcript ID · Participants (multi-select ou Person) · Durée (min) · Type (🧩/🎓/🎯/🤝) · Client / Deal (relation) · Sujets abordés · Synthèse (≤120 mots) · Phrases marquantes (prospect et client) · Next actions (🔹/🔸) · Résumé (2-3 lignes TL;DR) · Traité (case à cocher). Le transcript complet reste accessible (dans la fiche ou par le lien). Tout en puces.

## Format de sortie

1. **Type d'appel** + **Rattachement** (fiche, `[À VALIDER]`, ou « créée »)
2. **Synthèse** (5-8 puces, ≤120 mots)
3. **MAJ de la fiche** (ce qui change)
4. **Phrases marquantes** (prospect et client)
5. **Next actions** 🔹 Moi · 🔸 Autre


## Règles (non négociables)

1. **Tri d'abord** : le type est posé AVANT de synthétiser.
2. **Zéro invention** : incertain → `[À VALIDER]` / `[à caler]`.
3. **Ma voix** : net, sans tics IA, sans tiret cadratin.
4. **Synthèse bornée** : ≤120 mots, en puces.
5. **Aucune échéance hallucinée.**
6. **Phrases marquantes mot pour mot**, ou rien.

## Déclenchement type

En tâche planifiée, toutes les heures ou chaque soir selon le nombre de rendez-vous ; à la main sur un transcript ; avant un point projet ou hebdo pour consolider. Les tâches planifiées se déclenchent à heure fixe, pas à la fin d'un appel.

## Exemples et gabarit

Pour calibrer le rendu ou utiliser un gabarit, lire [exemples-et-template.md](references/exemples-et-template.md). Les exemples illustrent une méthode ; leurs chiffres, témoignages et dates ne sont pas des faits concernant l’utilisateur.
