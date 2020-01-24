# Commandes git

- git config --global user.name "John Doe"
- git config --global user.email johndoe@example.com
- git config --list
- git config --global color.diff auto
- git config --global color.status auto
- git config --global color.branch auto
- git config --global core.editor notepad++
- git config --global merge.tool vimdiff
- git init : initialise un dossier existant comme étant un dépôt git local
- git remote add [local_name] [distant_URL] : signale au dépôt git local de pointer vers un dépôt git distant
- git clone [distant_URL] : clone un dépôt distant dans un dépôt local (si le dossier est nouveau, dispense de git init / git remote add)
- git branch {-d} {-D} [new_branch_name] : liste les branches existantes {-d} supprime une branche {-D} force la suppression d'une branche [new_branch_name] crée une nouvelle branche avec le nom donné
- git checkout [branch_name] {8_first_digits_of_commit} [branch_name] switche de branche vers la branche nommée {commit_SHA} transporte vers le commit spécifié
- git add [file_name1] [file_name2] [folder] [etc.] : ajoute des fichiers ou des dossiers au commit futur
- git commit {-m "Message"} {--amend} {--no-edit} : commit les fichiers ajoutés au dépôt local {-m} ajoute un message simple {--amend} modifie le dernier commit {--no-edit} utilisé pour ajouter des fichiers au dernier commit
- git push : pousse les derniers commits locaux sur le dépôt distant
- git reflog : git log en plus poussé
- git status : statut actuel du dépôt local
- git stash {apply} {list} : crée une remise du code créé depuis le dernier commit {apply} applique la dernière remise
- git reset {--hard HEAD^} {--hard 8_first_digits_of_commit} {--mixed HEAD~} {--soft HEAD^} : enlève les commits sélectionnés du dépôt local, possibilité soit de faire un seul commit soit plusieurs soit d'aller directement au commit spécifié par son SHA. Différentes options : hard, enlève le code ajouté depuis, soft enlève les commits mais laisse le code, mixed entre les deux.
- git revert {HEAD^} : git reset pour le dépôt distant. Attention, zone dangereuse.
- accès SSH : pour ne pas avoir à réentrer ses identifiants à chaque push
- git blame [file_name] : permet de visualiser les modifications apportées à un fichier ligne par ligne
- git cherry-pick [commit1SHA] [commit2SHA] [etc.] permet de sélectionner uniquement les modifications de certains commits
- git merge [branch_name] : permet de merge deux branches ou une branche distante avec une locale
- git pull : permet de prendre le code du dépôt distant, équivalent de git fetch & git merge
- git fetch : prends l'historique du dépôt distant mais n'applique pas les modifications au dépôt local
- git rebase {-i} [commitSHA] => {pick, reword, edit, squash, fixup, exec, drop} : réarrange l'historique des commits locaux
- git bisect [start] [commit_endSHA] [commit_beginSHA] {good} {bad} : permet de tester différents commits pour traquer un bug
- git submodule add [remote_URL] : ajoute un composant d'un second dépôt distant dans le premier dépôt comme une fonctionnalité séparée
- git subtree push -P [repo_name] [repo_URL] [branch] : permet de traiter une branche comme une fonctionnalité séparée et la push sur un dépôt distant distinct
- git flow init : initialise gitflow
- git flow [branch_type] start [branch_name] : initialise un certain type de branche pour git flow
- forks : copie d'un dépôt distant existant non-modifiable en un dépôt distant personnel modifiable
- demandes de pull : pour le prompriétaire d'un dépôt (open-source par exemple), permet d'intégrer ou non les modifications proposées

# Commande vim
- i
- <esc>:wq
- <esc>:q!
- vimtutor depuis la commande principale

# Commande vimdiff pour mergetool
- cd ~ // vim .vimrc // i // set mouse=a // <esc>:wq
- git mergetool
- ]c // [c
- diffget {RE}{BA}{LO}