Preuve : Le résultat de git log --oneline -- acces.md permet de retrouver le commit associé au fichier. La commande git show permet d'examiner le commit et les modifications qu'il contient.

Explication : Un fichier non suivi n'apparaît pas dans le git diff ordinaire, car Git ne compare pas encore son contenu avec une version suivie. Après git add, le fichier entre dans l'index et git diff --cached affiche les changements préparés pour le prochain commit. Une fois le commit créé, git log --oneline -- acces.md permet de retrouver les commits associés à ce fichier.







git show --no-patch --format="%h %p %s" HEAD



Identifiant du commit de fusion : aa72d87

Premier parent : 92a906d

 Deuxième parent : 8f7934d





Les deux branches ont avancé indépendamment depuis un commit commun. La fusion `--no-ff` a créé un commit de fusion possédant deux parents. Aucun conflit n'est apparu, car 2 fichiers différents.



Fast-forward du TP 2, Git n'a pas seulement déplacé sur le `main` : il a créé un commit qui relie les deux historiques.

