# But
Dans ce TP nous allons mettre en place le workflow OpenSource.
Pour cela, mettez-vous en groupes de sorte d'avoir au moins deux ordinateurs par groupe.
L'un des ordinateurs fera office de mainteneur, l'autre sera contributeur.
Vous passerez d'un ordinateur à l'autre pour avancer dans le TP.

# Initialisation
## Mainteneur
A l'aide du bouton ![bouton ajout](https://github.com/user-attachments/assets/ed37ef03-ea7b-4ba8-acbf-43740891b89a) créer un nouveau dépot/repository.
Ouvrir l'onglet issue ![onglet issue](https://github.com/user-attachments/assets/c3de30a7-2921-4e86-b316-700dcbacc4ba) et créer en une nouvelle à l'aide du bouton ![bouton new issue](https://github.com/user-attachments/assets/6dd067e9-bf74-4f32-b42c-d0b77de6174d)
A côté du titre de l'issue se trouve un # suivi d'un numéro. Il s'agit de l'identifiant de l'issue, gardez le de côté :
![ID issue](https://github.com/user-attachments/assets/693f838c-843a-4a75-b837-00c5180dbe2a)


## Contributeur
Rendez-vous sur le dépôt créé par le mainteneur. 
Cette fois, le mainteneur **ne va pas** vous donner les droits de modification dessus.
Nous allons utiliser une nouvelle façon de transmettre nos modifications : les "pull requests".

Cliquez sur le bouton fork ![bouton fork](https://github.com/user-attachments/assets/f6c1d98a-d958-4caa-805b-2d1df98b35c5) en haut à droite pour dupliquer le dépôt dans votre espace personnel.

# Récupérer le dépôt sur notre machine
## Contributeur
Lancez [Github Desktop](https://github.com/apps/desktop?locale=fr-fr).
Ouvrez le menu "File" puis "Clone repository ...".
Connectez-vous à l'aide du bouton "Sign in" sur l'onglet "Github.com".
Sélectionnez le dépôt, l'endroit où le télécharger et cliquez sur le bouton "clone".

Github Desktop va s'occuper de tout configurer pour nous, notamment l'authentification.

Ouvrez le dossier où les sources ont été téléchargées, on va pouvoir créer des commits. 

# Notre 1ère PR
## Contributeur
Sur notre machine locale, créer une branche.
Sur cette branche, ajouter un nouveau commit.
Faire un `git push`. 
Un message apparaît, il nous explique que pour créer la branche sur le dépôt distant, il faut utiliser la commande `git push --set-upstream origin ` suivie du nom de la branche.
Faites-lui confiance.

```
Git permet d'avoir, pour un même projet, plusieurs dépôts distants.
Celui utilisé par défaut s'appelle par convention "origine" 
L'argument "--set-upstream origine" signifie donc : crée une branche sur le dépôt par défaut qui, dans notre cas, est Github
```

Rendez-vous sur Github, sur le dépôt dans votre espace personnel.
Un bandeau orange est apparu avec un bouton "Compare & pull request" ![bouton PR](https://github.com/user-attachments/assets/c1d1595f-3cb2-4a8a-9032-ac1e04a9d96e)
Cliquez dessus.

Il affiche une page qui rappelle les modifications.
On va associer cette pull request à l'issue créée précédemment.
Pour cela, suivez les instructions [ici](https://docs.github.com/fr/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue).

Envoyez la pull request avec le bouton ![bouton créer PR](https://github.com/user-attachments/assets/e3d30db7-9bfb-44e8-848d-6fa09db97184)

## Mainteneur
Ouvrir l'onglet pull request : ![onglet PR](https://github.com/user-attachments/assets/dc29c7da-4202-4ee3-80e5-3861d7fbaae7).
Une pull request doit apparaître. Ouvrez-la.
Pour la valider, cliquez sur le bouton merge: ![bouton merge](https://github.com/user-attachments/assets/396bffc8-57fc-42f0-8390-064463ba3d87)

# Récupérer les nouveautés
Maintenant, nous allons expérimenter le cas où des nouveautés apparaissent sur le dépôt d'origine.
## Mainteneur
Sur le dépôt d'origine, modifier le readme pour créer un nouveau commit.

## Contributeur
Rendez-vous sur le dépôt dans votre espace personnel sur la branche main. 
Le message "This branch is 1 commit behind" apparaît pour vous indiquer des nouveautés sur le dépôt d'origine.
Utilisez le bouton "sync fork" ![bouton sync fork](https://github.com/user-attachments/assets/656502ee-43cc-48bc-a77a-7fd79cd609dd) pour récupérer celles-ci.

Rendez-vous sur la branche "main" de votre dépôt local.
Récupérez les dernières modifications avec la commande `git pull`
Passez sur la branche créee précédemmment.
Rebasez celle-ci depuis master.
Déployer la dernière version de l'historique avec `git push -f`
