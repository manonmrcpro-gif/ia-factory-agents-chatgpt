# IA Factory — Agents pour Codex

12 skills en français issus de la bibliothèque Notion IA Factory. Version 1.0.0, adaptée le 22 septembre 2026. Chaque skill conserve sa méthode métier, ses données d’entrée et ses livrables ; les exemples et gabarits sont chargés séparément.

## Installer

Prérequis : Codex avec prise en charge des plugins, Git et un accès GitHub au dépôt privé. Accepter l’invitation au dépôt et authentifier Git pour ce compte. Aucun secret ne doit être copié dans un prompt ou dans ce dépôt.

Ajouter le dépôt comme marketplace :

```sh
codex plugin marketplace add manonmrcpro-gif/ia-factory-agents-chatgpt
```

Dans l’annuaire des plugins Codex, sélectionner cette marketplace (`personal` / `Personal`) puis installer **IA Factory — Agents**. Ouvrir ensuite une nouvelle tâche pour charger les skills. Si une autre marketplace porte déjà le nom `personal`, utiliser l’installation locale des skills ci-dessous pour éviter une collision.

Alternative locale : cloner le dépôt puis copier les dossiers de `plugins/ia-factory-agents/skills/` dans `~/.codex/skills/`, en vérifiant au préalable qu’aucun skill du même nom ne serait écrasé.

La procédure marketplace suit la [documentation officielle OpenAI](https://developers.openai.com/plugins/build/plugins).

## Les skills (12 agents + l'interview)

| Agent | Skill |
| --- | --- |
| Mes documents de référence (interview, à lancer en premier) | [documents-de-reference](plugins/ia-factory-agents/skills/documents-de-reference/SKILL.md) |
| Agent VoC (Voix du Client) | [voc-voix-du-client](plugins/ia-factory-agents/skills/voc-voix-du-client/SKILL.md) |
| Coach Process & IA | [coach-process-ia](plugins/ia-factory-agents/skills/coach-process-ia/SKILL.md) |
| Agent Analyse de call et closing | [closing-objections](plugins/ia-factory-agents/skills/closing-objections/SKILL.md) |
| Agent Cas Clients | [cas-clients](plugins/ia-factory-agents/skills/cas-clients/SKILL.md) |
| Agent Cadrage d'offre & Pricing | [cadrage-offre-pricing](plugins/ia-factory-agents/skills/cadrage-offre-pricing/SKILL.md) |
| Projet Lead Magnet | [lead-magnet-funnel](plugins/ia-factory-agents/skills/lead-magnet-funnel/SKILL.md) |
| Agent Chef de projet | [chef-de-projet](plugins/ia-factory-agents/skills/chef-de-projet/SKILL.md) |
| Agent Transcript to Drive/Notion + Next Actions | [transcript-next-actions](plugins/ia-factory-agents/skills/transcript-next-actions/SKILL.md) |
| Agent Sales | [sales-prep](plugins/ia-factory-agents/skills/sales-prep/SKILL.md) |
| Agent Rédaction | [redaction-contenu](plugins/ia-factory-agents/skills/redaction-contenu/SKILL.md) |
| Agent Stratégie édito | [strategie-edito](plugins/ia-factory-agents/skills/strategie-edito/SKILL.md) |
| Agent Propale | [propale](plugins/ia-factory-agents/skills/propale/SKILL.md) |

## Utilisation

Exemples de demandes :

- « Utilise $transcript-next-actions pour classer ce transcript et extraire les prochaines actions. »
- « Utilise $strategie-edito pour cadrer ma ligne éditoriale. »
- « Utilise $propale pour préparer une proposition à partir de ces notes de découverte. »

Commencer par « Utilise $documents-de-reference pour lancer mon interview » : il crée tes 3 documents de référence (ADN, méthode & économie ; Ma voix ; Mes règles IA). Ranger ensuite ADN, méthode & économie et Ma voix dans Notion ou Google Drive et brancher le connecteur, pour que les skills les lisent ; à défaut, les joindre. Joindre les autres documents utiles selon le skill (transcripts, VoC, fiches projet). Mes règles IA se collent dans les instructions personnalisées de ChatGPT. Ces documents propres à chaque utilisateur ne sont pas inclus. Les skills peuvent aussi être sélectionnés automatiquement selon la demande.

Notion et Drive sont optionnels : connecter son propre compte pour y lire ou mettre à jour les données. Sans connecteur, les skills travaillent sur les fichiers fournis et livrent du contenu prêt à intégrer. Le plugin ne contient aucun compte, aucune base client, aucun identifiant de connecteur et aucune automatisation active. Les messages sont préparés en brouillon, l’envoi ou la publication nécessite une demande explicite.

Chaînes possibles : Transcript → VoC → Stratégie édito → Rédaction ; Sales → Closing → Propale ; suivi de mission → Cas clients. Elles indiquent des passages de contexte, pas une exécution automatique.

## Sources et adaptation

[La bibliothèque Notion](https://app.notion.com/p/38e2b2d61b868316a57e01250a75b578) est la source métier. `catalogue.json` relie chaque skill à sa page et à sa date de modification. Aucun accès Notion à cette bibliothèque n’est nécessaire pour utiliser les skills installés.

Les instructions de branchement Claude/Dust ont été remplacées par un fonctionnement Codex avec fichiers et connecteurs disponibles. Les méthodes, garde-fous et gabarits ont été conservés. Ajustements explicites : formule net/CA rendue dépendante de l’assiette réelle des charges ; durée du guide Sales cohérente avec ses séquences ; métaphore des « trois cerveaux » identifiée comme telle ; arithmétique incohérente de l’exemple Propale corrigée. L’exemple externe embarqué de Propale n’est pas redistribué.

Le [plugin Claude](https://github.com/prevostjohanna/ia-factory-agents-claude) reste distribué séparément.

## Vérification

Les 11 SKILL.md et le manifeste Codex ont passé les validateurs officiels locaux à la création. Les références locales et la correspondance avec les 11 pages Notion ont été vérifiées. Cela valide le paquet, pas les résultats métier sur vos données ; les connexions Notion/Drive doivent être configurées chez chaque utilisateur.
