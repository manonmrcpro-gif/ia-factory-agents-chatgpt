# Tableau de bord et point hebdo

## D'où viennent les chiffres

Elle ne colle aucun lien de post. Tout ce qu'Apify peut récupérer, l'agent le récupère. Restent deux chiffres privés, ses impressions et ses visites de profil : l'agent va les lire lui-même dans son navigateur, elle n'a qu'à autoriser.

| Chiffre | D'où il vient | Qui le récupère |
|---|---|---|
| Ses posts de la semaine (texte, date, lien) | Apify, scraper de posts LinkedIn sans cookie, sur son propre profil | l'agent, chaque semaine |
| Réactions, commentaires, republications par post | même scraper | l'agent |
| **Noms des personnes qui commentent** (et leur commentaire) | Apify, scraper de commentaires sans cookie, sur ses posts des 2 dernières semaines | l'agent |
| **Noms des personnes qui likent** | Apify, scraper de réactions sans cookie, sur les mêmes posts | l'agent |
| **Nombre d'abonnés** de son profil | public : Apify, scraper de profil LinkedIn sans cookie | l'agent. **Abonnés gagnés** = différence avec le point précédent (le premier point sert de point de départ). Vérifier que le scraper choisi renvoie bien le nombre d'abonnés ; sinon, le lui demander avec les deux chiffres ci-dessous |
| Impressions, visites de profil | privés : seule elle les voit dans ses statistiques LinkedIn | **l'agent, avec le mode agent** : elle lance le point hebdo, se connecte elle-même à LinkedIn quand le mode agent le lui demande, l'agent lit les chiffres (voir « Les chiffres privés » ci-dessous). Sinon : elle envoie l'export de ses statistiques ou tape les deux chiffres |
| Inscrits au lead magnet | Brevo (connecteur, ou navigateur) | l'agent |
| Conversations ouvertes (messages privés, mails, visios) | elle, en une phrase au point hebdo | elle |
| Rendez-vous obtenus grâce au contenu | question « Comment tu m'as connue ? » dans son formulaire de prise de rendez-vous | l'agent lit les réponses |
| Clients signés et montant | son suivi commercial | l'agent lit la base |

**Pourquoi Apify ne donne pas les impressions** : LinkedIn ne les montre qu'à elle. Les scrapers qui les lisent demandent son cookie de session LinkedIn, c'est-à-dire l'accès à son compte : jamais (risque de restriction du compte). Le lui dire en une ligne si elle demande pourquoi ces deux chiffres passent par le navigateur.

**Le coût, à lui dire en une ligne** : une fois par semaine, sur ses posts des 2 dernières semaines, la récupération tient dans les 5 $ gratuits d'Apify (de l'ordre de 3 $ par mois pour une personne qui publie 4 fois par semaine ; ça dépend du nombre de réactions). Si elle veut une mise à jour **tous les jours**, c'est possible mais ça dépasse le gratuit : compter le plan Starter d'Apify (19 $ par mois), et une tâche planifiée quotidienne consomme aussi son quota d'utilisation de l'IA. Vérifier les prix sur l'onglet Pricing de chaque scraper avant de les lui annoncer.

Si son formulaire de prise de rendez-vous n'a pas la question « Comment tu m'as connue ? », le lui dire : c'est le seul chiffre qui relie le contenu au chiffre d'affaires.

## Les chiffres privés : comment l'agent les lit

- **Quand** : au point hebdo qu'elle lance elle-même (« fais mon point hebdo »), avec le mode agent. Le mode agent lui demande de se connecter à LinkedIn : c'est elle qui tape ses identifiants, jamais l'agent.
- **Vite** : les impressions dans les statistiques de contenu de son profil (période « 7 derniers jours »), les visites de profil sur la page des vues du profil (LinkedIn les donne sur 90 jours : noter le chiffre avec sa période). Si une adresse a changé, passer par son profil, section Statistiques.
- **Jamais** : rien publier, liker, commenter ni envoyer ; ne pas toucher aux réglages de son compte.
- **Si ça bloque** : lui proposer l'export (profil ➜ Statistiques ➜ « Afficher toutes les statistiques » ➜ impressions de posts ➜ Exporter) ou les deux chiffres tapés.

## Où c'est rangé

- **La base « Tableau de bord contenu »** du Hub Freelance, une ligne par semaine : Semaine, Début de semaine, Posts publiés, Impressions, Abonnés gagnés, Interactions (réactions + commentaires), Taux d'engagement (formule), Commentaires de la cible, Visites de profil, Inscrits lead magnet, Conversations ouvertes, RDV grâce au contenu, Clients signés, Montant signé, Post de la semaine, Arrête / Double / Teste, Elles commentent, Elles likent. À créer si elle n'existe pas ; ajouter les colonnes qui manquent sans toucher aux autres.
- **Les chiffres de chaque post** dans la base « Calendrier de contenu » (`Lien du post`, `Impressions`, `Réactions`, `Commentaires`, `Engagement`, `Statut` → Publié).
- **Le tableau de bord** (obligatoire) : la base Notion stocke, elle n'est pas le tableau de bord. À chaque point hebdo, l'agent montre un tableau de bord qui reprend toutes les stats de la base (dans un canevas s'il peut l'afficher, sinon en tableau) : en haut le post qui a le mieux marché, puis les chiffres de la semaine comparés à la semaine précédente, les résultats par pilier, par étape et par style, et les personnes chaudes.

## Le tableau de bord : toujours le même modèle

Modèle à suivre : `references/modele-tableau-de-bord.html` (exemple fictif d'Inès, consultante RH). Toutes les participantes ont la même structure : la reprendre telle quelle, dans cet ordre, avec ses données à elle. Pas de graphiques improvisés à la place.

1. **Le post de la semaine** : son hook, pilier, étape, style, source ; impressions, réactions, commentaires (dont ceux de la cible) ; son score « ×2,6 plus d'interactions que tes posts habituels » ; pourquoi il a **peut-être** marché ; le lien du post.
2. **En chiffres, avec deux onglets : la semaine et le mois** (4 dernières semaines), chacun comparé à la période d'avant : impressions, abonnés gagnés, interactions, taux d'engagement, commentaires de la cible, visites de profil, inscrits lead magnet, conversations ouvertes, RDV grâce au contenu, clients signés et montant. Chaque chiffre dit d'où il vient. Une ligne rappelle que la semaine bouge beaucoup et que le mois donne la tendance.
3. **Chaque post, lu selon son objectif** : lien du post, étape, ce sur quoi il est jugé, impressions, interactions, « vs tes posts habituels », et une **lecture en hypothèse** (« Flop ? Hook trop vu, ou mauvais jour ? »). Une ligne explique le score en mots simples : interactions du post ÷ celles d'un post typique d'elle (médiane de ses 15 derniers posts). Ne jamais écrire « médiane » seul sans l'expliquer.
4. **Par pilier, par étape, par style**, sur 4 semaines.
5. **Arrête ? / Double / Teste**, formulés en pistes, avec le résultat de ce qui avait été décidé au point précédent.
6. **Elles commentent / Elles likent** : lien du profil, contexte (avec le lien du commentaire), piste de conversation.
7. **À commenter cette semaine** : 3 posts récents, avec leur lien, de personnes chaudes ou de comptes suivis qui surperforment (récupérés par Apify), et pourquoi les commenter. Elle écrit le commentaire avec ses mots.
8. **D'où viennent les chiffres**, en pied de page.

**Lectures = hypothèses.** On n'est jamais sûr à 100 % de pourquoi un post a marché ou fait un flop : toujours un point d'interrogation ou un « peut-être », jamais un verdict.

## Le point hebdo

Même jour chaque semaine. Elle peut le lancer d'une phrase (« fais mon point hebdo »).

1. **Récupérer** les chiffres (tableau ci-dessus) : Apify d'abord, puis lire ses impressions et ses visites de profil dans son navigateur (ou, si ça bloque, son export). Les stocker dans la base et le calendrier, puis lui montrer le tableau de bord. Le point hebdo n'est pas fini tant qu'elle ne l'a pas vu.
2. **Lire chaque post selon son objectif.** Un TOFU se juge sur la portée et les abonnés gagnés. Un MOFU sur les commentaires de la cible et les messages privés. Un BOFU sur les inscriptions et les rendez-vous, même s'il fait peu de vues. On ne juge jamais un post isolé : un post vit plusieurs semaines sur LinkedIn, et quelques semaines de données, c'est peu.
3. **Les flops possibles** : un post sous la moitié de ce que font ses posts habituels. Proposer des causes possibles, en questions (le hook ? le sujet ? le format ? le jour ?) et dire si le sujet mérite une deuxième chance avec un autre hook.
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
