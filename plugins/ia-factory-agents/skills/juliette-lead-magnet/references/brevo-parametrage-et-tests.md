# Brevo : paramétrage qui marche, pièges vécus, test de bout en bout

À lire avant de paramétrer le formulaire, les attributs et l'automatisation. Chaque point ci-dessous a déjà fait perdre des heures.

## 1. Les attributs de contact (à créer d'abord)

Dans Brevo : Contacts > Paramètres > Attributs de contact. Type texte. Nom en majuscules, sans espace ni accent (SCORE_GLOBAL, pas « Score global »).

| Attribut | Contenu | Exemple |
|---|---|---|
| PROFIL | le code du profil | DEPENDANTE |
| SCORES | la note de chaque axe, dans l'ordre des axes, séparées par des virgules | 2,3,1,2 |
| SCORE_GLOBAL | le score global en pourcentage, sans le signe % | 47 |
| OU_TU_EN_ES | un code court (voir point 3) | ;q0a0;q2a1;sL1;oL2;vL3;yL3;fv; |

## 2. Les champs cachés du formulaire (sinon Brevo ignore tout)

Un attribut qui existe mais qui n'est pas déclaré dans le formulaire n'est **jamais** enregistré, même si la page l'envoie. Dans le constructeur du formulaire Brevo : ajouter chaque attribut en **champ caché**, puis republier le formulaire et recoller son code dans la page. La page remplit ces champs juste avant l'envoi.

Vérifier après un test : la fiche du contact de test doit montrer PROFIL, SCORES, SCORE_GLOBAL et OU_TU_EN_ES remplis.

## 3. La limite de caractères : envoyer un code, pas des phrases

Un champ texte du formulaire refuse au-delà d'environ 200 caractères, avec un message trompeur (« vérifie ton adresse mail »). Ne jamais envoyer de phrases dans un attribut. Envoyer un code court, et c'est l'email qui le retraduit en phrases :
- `;q{question}a{réponse};` pour les 2 ou 3 réponses à citer dans « Où tu en es » (numérotation à partir de 0) ;
- `{axe}L{niveau};` pour le niveau de chaque axe (1 = à travailler en premier, 2 = en construction, 3 = solide) ;
- `f{axe};` pour son axe le plus fort (le point d'appui).

## 4. La syntaxe des conditions dans l'email

```
{% if ";q0a1;" in contact.OU_TU_EN_ES %}La phrase qui correspond à cette réponse. {% endif %}
{% if contact.PROFIL == "DEPENDANTE" %}… bloc du profil …{% endif %}
```

Écrire `"x" in contact.ATTRIBUT`. Avec `contains`, Brevo n'envoie pas l'email du tout, sans aucun message d'erreur. Après chaque changement de conditions, refaire un test d'inscription.

## 5. L'automatisation

- Déclencheur : **Formulaire soumis** (choisir le formulaire du quiz). « Ajouté à une liste » ne se déclenche pas pour quelqu'un qui est déjà dans la liste. Autoriser la ré-entrée pour pouvoir retester avec la même adresse.
- Chaque étape « Envoyer un email » garde **sa propre copie** du message. Modifier le template dans la bibliothèque ne change pas ce qui part : il faut ouvrir l'étape, cliquer sur Modifier, corriger, « Utiliser ce modèle pour l'automatisation », puis Enregistrer l'étape.
- L'objet de l'email se modifie dans l'étape, pas dans le modèle.

## 6. Les graphiques dans l'email

- Radar et baromètre en image QuickChart (quickchart.io), avec les notes insérées depuis l'attribut : `…"data":[{{ contact.SCORES }}]…` dans l'adresse de l'image. Désactiver la légende automatique (`"legend":{"display":false}`) et écrire la légende en texte sous l'image.
- Ne jamais mettre de règle CSS globale `img { display: block }` : Gmail transforme les emojis en images, et l'emoji de la signature part seul à gauche.
- Tout centrer avec des tableaux (`align="center"`), pas seulement avec `margin: auto`.
- Mettre la police de la charte en ligne sur chaque paragraphe (`font-family` dans le `style`) : dans certains lecteurs, le texte dans les tableaux n'hérite pas de la police.

## 7. Le pied de page

Adresse postale de l'entreprise (obligatoire), vérifiée sur un registre officiel (societe.com, annuaire des entreprises) plutôt que recopiée d'un vieux document. Lien de désinscription : `{{ unsubscribe }}`.

## 8. Le test de bout en bout (fait par l'IA, avant de rendre la main)

1. Ouvrir la page en ligne, répondre au quiz, s'inscrire avec une adresse de test (alias `prenom+test1@gmail.com` : chaque test a un alias neuf).
2. Vérifier la fiche du contact dans Brevo : tous les attributs remplis.
3. Attendre l'email (une à deux minutes), le lire (connecteur Gmail ou navigateur) : objet, graphiques, phrases tirées des réponses, lecture par axe, signature centrée, liens.
4. Si l'email n'arrive pas alors que le contact est entré dans l'automatisation : chercher d'abord une condition mal écrite (point 4).
5. À la fin, donner à l'utilisateur la liste des contacts de test à supprimer (l'IA ne supprime pas elle-même).
