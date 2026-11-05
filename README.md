# IA Factory : Agents pour Codex

15 skills en français (14 agents + l'interview) issus de la bibliothèque Notion IA Factory. Version 1.0.0, adaptée le 22 septembre 2026. Chaque skill conserve sa méthode métier, ses données d’entrée et ses livrables ; les exemples et gabarits sont chargés séparément.

## Installer

Prérequis : Codex avec prise en charge des plugins, Git et un accès GitHub au dépôt privé. Accepter l’invitation au dépôt et authentifier Git pour ce compte. Aucun secret ne doit être copié dans un prompt ou dans ce dépôt.

Ajouter le dépôt comme marketplace :

```sh
codex plugin marketplace add manonmrcpro-gif/ia-factory-agents-chatgpt
```

Dans l’annuaire des plugins Codex, sélectionner cette marketplace (`personal` / `Personal`) puis installer **IA Factory : Agents**. Ouvrir ensuite une nouvelle tâche pour charger les skills. Si une autre marketplace porte déjà le nom `personal`, utiliser l’installation locale des skills ci-dessous pour éviter une collision.

Alternative locale : cloner le dépôt puis copier les dossiers de `plugins/ia-factory-agents/skills/` dans `~/.codex/skills/`, en vérifiant au préalable qu’aucun skill du même nom ne serait écrasé.

La procédure marketplace suit la [documentation officielle OpenAI](https://developers.openai.com/plugins/build/plugins).

## Les skills (14 agents + l'interview)

| Agent | Skill |
| --- | --- |
| Florence, tes Documents de référence (interview, à lancer en premier) | [florence-documents-de-reference](plugins/ia-factory-agents/skills/florence-documents-de-reference/SKILL.md) |
| Constance, ta Maintenance | [constance-maintenance](plugins/ia-factory-agents/skills/constance-maintenance/SKILL.md) |
| Aya, ta Voix du client | [aya-voix-du-client](plugins/ia-factory-agents/skills/aya-voix-du-client/SKILL.md) |
| Nadia, ta Coach Process et IA | [nadia-coach-process-ia](plugins/ia-factory-agents/skills/nadia-coach-process-ia/SKILL.md) |
| Nicole, ton Analyse de call | [nicole-analyse-call](plugins/ia-factory-agents/skills/nicole-analyse-call/SKILL.md) |
| Serena, tes Cas clients | [serena-cas-clients](plugins/ia-factory-agents/skills/serena-cas-clients/SKILL.md) |
| Joséphine, ton Cadrage offre et pricing | [josephine-cadrage-offre](plugins/ia-factory-agents/skills/josephine-cadrage-offre/SKILL.md) |
| Juliette, ton Lead Magnet | [juliette-lead-magnet](plugins/ia-factory-agents/skills/juliette-lead-magnet/SKILL.md) |
| Colette, ta Cheffe de projet | [colette-cheffe-de-projet](plugins/ia-factory-agents/skills/colette-cheffe-de-projet/SKILL.md) |
| Tina, ton Transcript | [tina-transcript](plugins/ia-factory-agents/skills/tina-transcript/SKILL.md) |
| Berthe, ta Préparation RDV découverte | [berthe-preparation-rdv](plugins/ia-factory-agents/skills/berthe-preparation-rdv/SKILL.md) |
| Simone, ta Coach rédaction | [simone-coach-redaction](plugins/ia-factory-agents/skills/simone-coach-redaction/SKILL.md) |
| Coco, ta Stratégie édito | [coco-strategie-edito](plugins/ia-factory-agents/skills/coco-strategie-edito/SKILL.md) |
| Nawal, ta Propale | [propale](plugins/ia-factory-agents/skills/nawal-propale/SKILL.md) |
| Mireille, ta Veille offres de mission | [mireille-veille-missions](plugins/ia-factory-agents/skills/mireille-veille-missions/SKILL.md) |

## Le socle commun

Chaque agent suit le même socle : il annonce en démarrant à quoi il sert, où il lit et où il range, et s'il s'utilise tel quel ou se personnalise ; il vérifie ses sources et ne crée rien en double ; il explique chaque outil qu'il fait entrer ; il va chercher l'info dans le mode agent plutôt que de demander des captures ; il rend le process en fin de séance (gris = l'IA, rose = à la main, goulots signalés) ; il finit par « Où on en est ». Aucun agent ne rédige un message à copier-coller pour une personne réelle : il suggère une piste, tu écris.

## Utilisation

Exemples de demandes :

- « Utilise $tina-transcript pour classer ce transcript et extraire les prochaines actions. »
- « Utilise $coco-strategie-edito pour construire mon calendrier de contenu du mois. »
- « Utilise $nawal-propale pour préparer une proposition à partir de ces notes de découverte. »

Commencer par « Utilise $florence-documents-de-reference pour lancer mon interview » : il crée tes 3 documents de référence (ADN, méthode & économie ; Ma voix ; Mes règles IA). Ranger ensuite ADN, méthode & économie et Ma voix dans Notion ou Google Drive et brancher le connecteur, pour que les skills les lisent ; à défaut, les joindre. Joindre les autres documents utiles selon le skill (transcripts, VoC, fiches projet). Mes règles IA se collent dans les instructions personnalisées de ChatGPT. Ces documents propres à chaque utilisateur ne sont pas inclus. Les skills peuvent aussi être sélectionnés automatiquement selon la demande.

Notion et Drive sont optionnels : connecter son propre compte pour y lire ou mettre à jour les données. Sans connecteur, les skills travaillent sur les fichiers fournis et livrent du contenu prêt à intégrer. Le plugin ne contient aucun compte, aucune base client, aucun identifiant de connecteur et aucune automatisation active. Les messages sont préparés en brouillon, l’envoi ou la publication nécessite une demande explicite.

Chaînes possibles : Aya, ta Voix du client → Coco, ta Stratégie édito → Simone, ta Coach rédaction ; Mireille, ta Veille offres de mission → Berthe, ta Préparation RDV découverte → Nicole, ton Analyse de call → Nawal, ta Propale ; Tina, ton Transcript → Colette, ta Cheffe de projet → Serena, tes Cas clients. Elles indiquent des passages de contexte, pas une exécution automatique.

## Sources et adaptation

[La bibliothèque Notion](https://app.notion.com/p/38e2b2d61b868316a57e01250a75b578) est la source métier. `catalogue.json` relie chaque skill à sa page et à sa date de modification. Aucun accès Notion à cette bibliothèque n’est nécessaire pour utiliser les skills installés.

Les instructions de branchement Claude/Dust ont été remplacées par un fonctionnement Codex avec fichiers et connecteurs disponibles. Les méthodes, garde-fous et gabarits ont été conservés. Ajustements explicites : formule net/CA rendue dépendante de l’assiette réelle des charges ; durée du guide Préparation RDV découverte cohérente avec ses séquences ; métaphore des « trois cerveaux » identifiée comme telle ; arithmétique incohérente de l’exemple Propale corrigée. L’exemple externe embarqué de Propale n’est pas redistribué.

Le [plugin Claude](https://github.com/prevostjohanna/ia-factory-agents-claude) reste distribué séparément.

## Vérification

Les 11 SKILL.md et le manifeste Codex ont passé les validateurs officiels locaux à la création. Les références locales et la correspondance avec les 11 pages Notion ont été vérifiées. Cela valide le paquet, pas les résultats métier sur vos données ; les connexions Notion/Drive doivent être configurées chez chaque utilisateur.
