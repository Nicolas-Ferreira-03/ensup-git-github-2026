Preuve : Le résultat de git log --oneline -- acces.md permet de retrouver le commit associé au fichier. La commande git show permet d'examiner le commit et les modifications qu'il contient.

Explication : Un fichier non suivi n'apparaît pas dans le git diff ordinaire, car Git ne compare pas encore son contenu avec une version suivie. Après git add, le fichier entre dans l'index et git diff --cached affiche les changements préparés pour le prochain commit. Une fois le commit créé, git log --oneline -- acces.md permet de retrouver les commits associés à ce fichier.







git show --no-patch --format="%h %p %s" HEAD



Identifiant du commit de fusion : aa72d87

Premier parent : 92a906d

Deuxième parent : 8f7934d





Les deux branches ont avancé indépendamment depuis un commit commun. La fusion --no-ff a créé un commit de fusion possédant deux parents. Aucun conflit n'est apparu, car 2 fichiers différents.



Fast-forward du TP 2, Git n'a pas seulement déplacé sur le main : il a créé un commit qui relie les deux historiques.

L'enregistrement dans l'éditeur sauvegarde les données sur le disque,  git add prépare ces données pour le contrôle de version.

Inscription sur place sera manquante puisque pas ajouter a la préparation du commit.


$ git log --oneline
a70f9f8 (HEAD -> main) docs: preciser les conditions d acces
5fe8032 docs: presenter le forum ENSUP
e701aa5 (origin/main, origin/HEAD) Retirer les dates et presenter le contenu comme un module
c0bafa4 Harmoniser les supports ENSUP et preciser les deux types de PR
8fa44d0 Preparer les TP ENSUP et la collecte des rendus

ferr3@PC-Nico MINGW64 ~/ensup-git-github-2026/rendus/Nicolas-Ferreira-03 (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Mes-preuves.md
        Nicolas-Ferreira-03.md
        journal.md

nothing added to commit but untracked files present (use "git add" to track)

ferr3@PC-Nico MINGW64 ~/ensup-git-github-2026/rendus/Nicolas-Ferreira-03 (main)
$ git ls-files
README.md





**Ma prédiction :** `git diff` affiche les modifications apportées aux fichiers add a Git, mais qui n'ont pas encore commit


Parce que git diff compare normalement les modifications des fichiers suivis dans le répertoire de travail avec leur version dans l'index. Un fichier non suivi n'a pas encore été intégré à cet ensemble de comparaison. Après git add, son contenu est dans l'index et git diff --cached permet de voir ce qui sera enregistré.



Non pas visible , le commit appartient à la branche feature/programme et main n'a pas encore intégré cette évolution.

Partie 4 TP2

Dans le main
cat programme.md

avant 

A---B  main
     \
      C  feature/programme

apres

A---B---C  main, feature/programme


        C  feature/accessibilite
       /
A --- B
       \
        D  main



        C ---------+
       /            \
A --- B              M  main
       \            /
        D ---------+
                     \
                      feature/accessibilite pointe toujours sur C



Fast-forward du TP 2 : main n'avait pas avancé indépendamment. Git a simplement déplacé son pointeur vers le commit de la fonctionnalité. Aucun commit de fusion supplémentaire n'était nécessaire.




Fusion sans fast-forward ici : main et feature/accessibilite ont chacune leur propre commit. Git crée un commit de fusion avec deux parents.



Pourquoi aucun conflit ? Les commits modifient des fichiers distincts. Une divergence ne provoque pas automatiquement un conflit


https://github.com/AbidHamza/ensup-git-github-2026/pull/8


Un fork est une copie du dépôt hébergée sur GitHub lié au projet mère.

Un clone est une copie locale du dépôt sur mon ordinateur.

Une branche est une sous partie d'un dépôt, qui permet de travailler sans modifier la branche principale.




Permission denied :

Diagnostic : l'URL du dépôt distant peut envoyer vers un dépôt pour lequel je n'ai pas les droits d'écriture, ou le compte authentifié peut être incorrect.

Commande de contrôle : `git remote -v`



Non-fast-forward :

Diagnostic : le dépôt distant contient des commits absents de ma branche locale. Git refuse le push pour protéger l'historique distant.

Commande de contrôle : `git fetch origin`



Nothing to commit

Diagnostic : le fichier n'a peut-être pas été enregistré, il peut être ignoré, se trouver dans un autre dossier ou avoir déjà été commité.

Commande de contrôle : `git status --short`

