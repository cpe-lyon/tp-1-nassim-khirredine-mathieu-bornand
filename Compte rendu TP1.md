# Rendu TP1 - Nassim KHIRREDINE & Matthieu BORNAND


#### Exercice 2
##### Manuel

1. A l’aide du manuel, identifiez le rôle de la commande which
- La commande which affiche le chemin complet des commandes (shell).
2. Quand on consulte une page du manuel, comment peut-on rechercher un terme (par exemple, chercher le terme option dans la page de manuel de which?
- En tapant ```man which /termerecherché```
3. On quitte le manuel en tapant ```q```
4. Cette section parle des jeux et des programmes funs disponibles sur le système. (man N°section intro

##### Navigation dans l’arborescence des fichiers

1. ```cd /var/log```
2. ```cd ..```
3. ```cd```
4. ```cd -```
5. Impossible, nous n'avons pas les droits
6. De notre côté ça nous met ```sudo: cd: command not found```. Car la commande ```cd``` est intégrée au shell. Il faut donc faire ```sudo -i``` et ensuite ```cd /root``` .
7. * mkdir -p dossier1/fichier1
    * mkdir -p dossier2/dossier2.2/fichier2
    * mkdir dossier2/dossier2.2/fichier3
    * mkdir dossier2/dossier2.1
8. ```rm: cannot remove 'dossier1/fichier1': Is a directory```
9. Il faut ajouter ```-d```, par exemple: ```rm -d dossier1```
10. ```rm: cannot remove 'dossier2' : Directory not empty```
11. Il faut ajouter ```-r```, pour supprimer le contenu récursivement. Par exemple: ```rm -d -r dossier2```

##### Commandes importantes
1. En tapant ```date```.La commande ```time``` sert à chronométrer une tâche.
2. Les fichiers commençant par un "." sont les fichiers cachés.
3. ```which ls```
4. Non il n'existe pas d'entrée manuel pour cette commande. C'est l'alias de la commande ```ls -alF``` .
5. ```ll /usr/bin```
6. Ca affiche le contenu du répertoire parent.
7. ```pwd```
8. La première fois elle écrit 'yo' dans le fichier 'plop' et la deuxième fois elle remplace le contenu du fichier 'plop' par 'yo'.
9. Elle concatène le fichier 'plop' par 'yo' lorsqu'on l'éxecute 2 fois, le contenu du fichier sera donc 'yoyo'.
10. Cette commande permet de déterminer le type d'un fichier.
11. Le contenu a aussi été remplacé dans le fichier "titi". Lorsqu'on supprime le fichier "toto", le fichier "titi" reste.
12. Ca a aussi changé le contenu de "tutu". En inversant, ça change aussi le contenu de "titi". Ca a supprimé les deux fichiers.
13. ```CTRL + S``` permet d'arrêter le défilement et ```CTRL + Q``` permet de le reprendre.
14. Pour afficher les 5 premières lignes : ```head -5 /var/log/syslog``` et pour afficher les 15 dernières : ```tail -15 /var/log/syslog``` .
15. La commande ```less``` permet de visualiser un fichier texte page par page.
16. ```cat /etc/passwd``` permet d'afficher les utilisateurs et certains informations relatives. Pour afficher la page manuel : ```man 5 intro```
17. ```cut -d: -f1 /etc/passwd | sort -r```
18. ```cat /etc/passwd | wc``` et on a 32 utilisateurs.
19. ```man -k conversion | wc -l``` on obtient donc 4.
20. ```find . -name passwd```
21. ```find . name passwd >> ~/list_passwd_files.txt 2>>/dev/null```
22. Dans votre dossier personnel, utilisez la commande grep pour chercher où est défini l’alias ll vu précédemment
- ```grep -r "alias ll"``` 
23. Utilisez la commande locate pour trouver le fichier history.log.
- ```locate history.log```
24. Créer un fichier dans votre dossier personnel puis utilisez locate pour le trouver. Apparaît-il? Pourquoi?
- Non le fichier n'apparait pas car il a été créé après la dernière mise à jour de la base de données de ```locate```

#### Exercice 4

3. Cette question ne nécessite pas de réponse bien qu'il y ai le signe disant le contraire dans le TP.

4. La variable PS1 servant à mettre en forme l'invite de commande à était remplacé par la ligne suivante : 
- ```\e[91m[\A] \e[00m- \e[92m\u@\h\e[00m:\e[96m\w\e[00m$```

[screen Exo4Q4](/img/inviteCommande_Exo4Q4.png)
