Git Cheat Sheet Français
===============


### Index
* [Créer](#créer)
* [Modifications locales](#modifications-locales)
* [Historique de Commit](#historique-de-commit)
* [Branches & Tags](#branches--tags)
* [Mises à jours & Publications](#mise-à-jours--publication)
* [Merge & Rebase](#merge--rebase)
* [Annulation](#annulation)

<hr>
### Créer

Cloner un repository existant :
```
$ git clone ssh://user@domain.com/repo.git
```

Créer un nouveau repository local :
```
$ git init
```

<hr>
### Modifications locales

Fichiers modifiés dans votre répertoire de travail :
```
$ git status
```

Modifications sur les fichiers suivis :
```
$ git diff
```

Ajouter tous les changements actuelles au prochain commit :
```
$ git add
```

Ajouter certains changements dans &lt;file&gt; au prochain commit :
```
$ git add -p <file>
```

Committer tous les changements locaux des fichiers suivis :
```
$ git commit -a
```

Committer les changements précédemment mis en scène :
```
$ git commit
```

Committer avec un message :
```
$ git commit -m 'message here'
```

Modifier le précédent commit :<br>
<em><sub>Ne modifié jamais un commit déjà publier sur un serveur !</sub></em>
```
$ git commit --amend
```

<hr>
### Historique de Commit

Afficher tous les commits, en partant du plus récent (cela montrera le hash, les informations de l'auteurs, la date du commit et le titre du commit) :
```
$ git log
```

Afficher tous les commits (cela montrera seulement le commit et le message du commit) :
```
$ git log --oneline
```

Afficher tous les commits d'un utilisateur :
```
$ git log --author="username"
```

Afficher l'historiques des modifications effectuées sur un fichier :
```
$ git log -p <file>
```

Qui a modifié quoi et quand dans une fichier &lt;file&gt; :
```
$ git blame <file>
```

<hr>
### Branches & Tags

Lister toutes les branches existantes :
```
$ git branch
```

Changer de branche :
```
$ git checkout <branch>
```

Créer une nouvelle branche en se basant sur le HEAD courrant :
```
$ git branch <new-branch>
```

Créer une nouvelle branche de suivi, basée sur une branche distante :
```
$ git branch --track <new-branch> <remote-branch>
```

Supprimer une branche locale :
```
$ git branch -d <branch>
```

Marqué le commit courrant avec un tag :
```
$ git tag <tag-name>
```

<hr>
### Mises à jours & Publications

Lister tout les dépôts distants configurés :
```
$ git remote -v
```

Monter les informations d'un dépôt distant :
```
$ git remote show <remote>
```

Ajouter un nouveau dépôt, nommé &lt;remote&gt; :
```
$ git remote add <remote> <url>
```

Télécharger toutes les modifications d'un dépôt distant nommé &lt;remote&gt;, mais ne pas les intégrer dans le HEAD :
```
$ git fetch <remote>
```

Télécharger les modifications et les fusionner/integrer directement dans le HEAD :
```
$ git remote pull <remote> <url>
```

Récupérer toutes les modifcations du HEAD dans le dépôt local :
```
$ git pull origin master
```

Publier les modifications locales sur un dépôt distant :
```
$ git push remote <remote> <branch>
```

Supprimer une branche sur un dépôt distant :
```
$ git push <remote> :<branch>
```

Publier les tags :
```
$ git push --tags
```

<hr>
### Merge & Rebase

Fusionner la branche <branch> dans le HEAD courrant :
```
$ git merge <branch>
```

Rebaser le HEAD courrant odans &lt;branch&gt; :<br>
<em><sub>Ne rebasé pas des commit publiés !</sub></em>
```
$ git rebase <branch>
```

Annuler un rebase :
```
$ git rebase --abort
```

Continuer un rebase après avoir résolu des conflits :
```
$ git rebase --continue
```

Utiliser votre outil de résolution de conflits configuré pour résoudre les conflits :
```
$ git mergetool
```

Utiliser votre éditeur de texte pour manuellement résoudre les conflits et (après les avoirs résolu) marquer le fichier résolu :
```
$ git add <resolved-file>
```
```
$ git rm <resolved-file>
```

<hr>
### Annulation

Annuler toutes les modifications dans le répertoire de travail :
```
$ git reset --hard HEAD
```

Retirer tous les fichiers de la fille d'attente  (i.e. annuler le dernier `git add`) :
```
$ git reset HEAD
```

Annuler les modifcations locales d'un fichier spécifique :
```
$ git checkout HEAD <file>
```

Annuler un commit  (en créant un nouveau commit avec des modifications inverses)  :
```
$ git revert <commit>
```

Placer le pointeur du HEAD sur un commit précédent et annuler toutes les modifications effectuées depuis :
```
$ git reset --hard <commit>
```

Placer le pointeur du HEAD sur un commit précédent et conserver toutes les modifications effectuées depuis en tant que modification en attente :
```
$ git reset <commit>
```

Placer le pointeur du HEAD sur un commit précédent et conserver les modifications locales non commité :
```
$ git reset --keep <commit>
```

<hr>

Source : https://framagit.org/ErwanT/Git-Cheat-Sheet/blob/master/Git%20Cheat%20Sheet-Fr.md