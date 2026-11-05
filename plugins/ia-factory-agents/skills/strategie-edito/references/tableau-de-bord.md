# Tableau de bord et point hebdo

## D'où viennent les chiffres

Elle ne colle aucun chiffre et aucun lien de post. Les chiffres viennent de trois endroits.

| Chiffre | D'où il vient | Qui le récupère |
|---|---|---|
| Ses posts de la semaine (texte, date, lien) | Apify, scraper de posts LinkedIn sans cookie, sur son propre profil | l'agent, chaque semaine |
| Réactions, commentaires, republications par post | même scraper | l'agent |
| **Noms des personnes qui commentent** (et leur commentaire) | Apify, scraper de commentaires sans cookie, sur ses posts des 2 dernières semaines | l'agent |
| **Noms des personnes qui likent** | Apify, scraper de réactions sans cookie, sur les mêmes posts | l'agent |
| Impressions, abonnés gagnés, visites de profil | privés : statistiques LinkedIn de son compte | l'agent, avec le mode agent dans son navigateur, ou elle exporte ses statistiques |
| Inscrits au lead magnet | Brevo (connecteur, ou navigateur) | l'agent |
| Conversations ouvertes (messages privés, mails, visios) | elle, en une phrase au point hebdo | elle |
| Rendez-vous obtenus grâce au contenu | question « Comment tu m'as connue ? » dans son formulaire de prise de rendez-vous | l'agent lit les réponses |
| Clients signés et montant | son suivi commercial | l'agent lit la base |

**Le coût, à lui dire en une ligne** : une fois par semaine, sur ses posts des 2 dernières semaines, la récupération tient dans les 5 $ gratuits d'Apify (de l'ordre de 3 $ par mois pour une personne qui publie 4 fois par semaine ; ça dépend du nombre de réactions). Si elle veut une mise à jour **tous les jours**, c'est possible mais ça dépasse le gratuit : compter le plan Starter d'Apify (19 $ par mois), et une tâche planifiée quotidienne consomme aussi son quota d'utilisation de l'IA. Vérifier les prix sur l'onglet Pricing de chaque scraper avant de les lui annoncer.

Si son formulaire de prise de rendez-vous n'a pas la question « Comment tu m'as connue ? », le lui dire : c'est le seul chiffre qui relie le contenu au chiffre d'affaires.

## Où c'est rangé

- **La base « Tableau de bord contenu »** du Hub Freelance, une ligne par semaine : Semaine, Posts publiés, Impressions, Abonnés gagnés, Réactions, Commentaires, Taux d'engagement (interactions ÷ impressions), Commentaires de la cible, Visites de profil, Inscrits au lead magnet, Conversations ouvertes, Rendez-vous grâce au contenu, Clients signés (montant), Post de la semaine, Arrête / Double / Teste. À créer si elle n'existe pas ; ajouter les colonnes qui manquent sans toucher aux autres.
- **Les chiffres de chaque post** dans la base « Calendrier de contenu » (`Lien du post`, `Impressions`, `Réactions`, `Commentaires`, `Engagement`, `Statut` → Publié).
- **L'interface** : la base Notion fait foi. À chaque point hebdo, l'agent en montre la lecture en tableau (ou dans un canevas s'il peut l'afficher) : en haut le post qui a le mieux marché, puis les chiffres de la semaine comparés à la semaine précédente, les résultats par pilier, par étape et par style, et les personnes chaudes.

## Le point hebdo

Même jour chaque semaine. Elle peut le lancer d'une phrase (« fais mon point hebdo »).

1. **Récupérer** les chiffres (tableau ci-dessus) et mettre à jour la base et le calendrier.
2. **Lire chaque post selon son objectif.** Un TOFU se juge sur la portée et les abonnés gagnés. Un MOFU sur les commentaires de la cible et les messages privés. Un BOFU sur les inscriptions et les rendez-vous, même s'il fait peu de vues. On ne juge jamais un post isolé : un post vit plusieurs semaines sur LinkedIn, et quelques semaines de données, c'est peu.
3. **Les flops** : un post sous la moitié de sa médiane habituelle. Chercher la cause probable (le hook, le sujet, le format, le jour) et dire si le sujet mérite une deuxième chance avec un autre hook.
4. **Arrête / double / teste** : une chose à arrêter, une chose à doubler, une chose à tester la semaine suivante. Pas plus. Présentées comme des pistes.
5. **Comparer avec le point précédent** : ce qui avait été décidé, ce que ça a donné.
6. **Les personnes chaudes**, en deux listes séparées, filtrées sur sa cible (titre, entreprise, secteur) :
   - **Elles commentent** : les personnes de la cible qui ont commenté cette semaine ou plusieurs fois récemment, avec ce qu'elles ont écrit.
   - **Elles likent** : les personnes de la cible qui ont liké plusieurs de ses posts récents.
   Pour chacune, **une piste de conversation formulée pour elle** : « Tu pourrais lui demander… », appuyée sur ce que la personne a vraiment écrit ou sur son poste. Exemple : « Sarah L. a commenté 3 de tes posts. Mardi, elle disait galérer à fixer ses prix. Tu pourrais lui demander où elle en est sur ses tarifs. » **Jamais de message rédigé, jamais une phrase entre guillemets à copier-coller** : elle écrit avec ses mots. Le principe, à rappeler une seule fois : un message court, qui pose une question simple, facile à répondre, sans pitch.
7. **Les conversations de la semaine** : combien de messages privés, mails et visios ouverts grâce au contenu. Les conversations créent les clients.
8. **Ajuster le calendrier** des semaines suivantes sans descendre sous les minimums du mix, et dire ce qui a changé et pourquoi.

## Le mois suivant

Le calendrier du mois 2 part du tableau de bord : les sujets et formats qui ont surperformé reviennent sous un autre angle ou un autre format, un post qui a très bien marché il y a 2 ou 3 mois peut être republié, un bon sujet qui a fait un flop revient avec un nouveau hook.
