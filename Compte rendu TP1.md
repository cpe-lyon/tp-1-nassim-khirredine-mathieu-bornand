# Rendu TP1 - Nassim KHIRREDINE & Matthieu BORNAND


#### Exercice 2
##### Manuel

1. A l’aide du manuel, identifiez le rôle de la commande which
- La commande which affiche le chemin complet des commandes (shell).
2. Quand on consulte une page du manuel, comment peut-on rechercher un terme (par exemple, chercher le terme option dans la page de manuel de which?
- En tapant ```man which /termerecherché```
3. Comment quitte-t-on le manuel ?
- On quitte le manuel en tapant ```q```
4. Chaque section du manuel a une première page, qui présente le contenu de la section. Aﬀicher la première page de la section 6; de quoi parle cette section?
- Cette section parle des jeux et des programmes funs disponibles sur le système. (man N°section intro)

##### Navigation dans l’arborescence des fichiers

1. allez dans le dossier /var/log : ```cd /var/log```
2. remontez dans le dossier parent (/var) en utilisant un chemin relatif : ```cd ..```
3. retournez dans le dossier personnel : ```cd```
4. revenez au dossier précédent (/var) **sans utiliser de chemin** ```cd -```
5. essayez d’accéder au dossier /root; que se passe-t-il? 
- Impossible, nous n'avons pas les droits
6. essayez la commande sudo cd /root; que se passe-t-il? Expliquez
- De notre côté ça nous met ```sudo: cd: command not found```. Car la commande ```cd``` est intégrée au shell. Il faut donc faire ```sudo -i``` et ensuite ```cd /root``` .
7. à partir de votre dossier personnel, créez l’arborescence suivante : (voir image TP1)
* mkdir -p dossier1/fichier1
    * mkdir -p dossier2/dossier2.2/fichier2
    * mkdir dossier2/dossier2.2/fichier3
    * mkdir dossier2/dossier2.1
8. revenez dans votre dossier personnel; à l’aide de la commande rm, essayez de supprimer Fichier1, puisDossier1; que se passe-t-il?
- ```rm: cannot remove 'dossier1/fichier1': Is a directory```
9. quelle commande permet de supprimer un dossier?
- Il faut ajouter ```-d```, par exemple: ```rm -d dossier1```
10. que se passe-t-il quand on applique cette commande à Dossier2?
- ```rm: cannot remove 'dossier2' : Directory not empty```
11.  Comment supprimer en une seule commande Dossier2 et son contenu?
- Il faut ajouter ```-r```, pour supprimer le contenu récursivement. Par exemple: ```rm -d -r dossier2```

##### Commandes importantes
1. Quelle commande permet d’aﬀicher l’heure? A quoi sert la commande time?
- En tapant ```date```.La commande ```time``` sert à chronométrer une tâche.
2. Dans votre dossier personnel, tapez successivement les commandes ls puis la; que peut-on en déduire sur les fichiers commençant par un point?
- Les fichiers commençant par un "." sont les fichiers cachés.
3. Où se situe le programmels?
- ```which ls```
4. Essayez la commande ll. Existe-t-il une entrée de manuel pour cette commande? Utilisez les commandes alias ou alias pour en savoir plus sur la nature de cette commande.
- Non il n'existe pas d'entrée manuel pour cette commande. C'est l'alias de la commande ```ls -alF``` .
5. Quelle commande permet d’afficher les fichiers contenus dans le dossier/bin? 
- ```ll /usr/bin```
6. Que fait la commandels .. ? 
- Ca affiche le contenu du répertoire parent.
7. Quelle commande donne le chemin complet du dossier courant?
- ```pwd```
8. Que fait la commande echo 'yo' > plop exécutée 2 fois?
- La première fois elle écrit 'yo' dans le fichier 'plop' et la deuxième fois elle remplace le contenu du fichier 'plop' par 'yo'.
9. Que fait la commande echo 'yo' >> plopexécutée 2 fois?
- Elle concatène le fichier 'plop' par 'yo' lorsqu'on l'éxecute 2 fois, le contenu du fichier sera donc 'yoyo'.
10. A quoi sert la commandefile? Essayez la sur des fichiers de types différents
- Cette commande permet de déterminer le type d'un fichier.
11. Créez un fichier toto qui contient la chaîne Hello Toto !; créer ensuite un lien titiv ers ce fichier avec la commande ln toto titi. Modifiez à présent le contenu de toto et affichez le contenu detiti: qu’observe-t-on? Supprimez le fichier toto; quelle conséquence cela a-t-il sur titi?
- Le contenu a aussi été remplacé dans le fichier "titi". Lorsqu'on supprime le fichier "toto", le fichier "titi" reste.
12. Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le contenu de titi; quelle conséquence pour tutu? Et inversement? Supprimez le fichier titi; quelle conséquence cela a-t-il sur tutu?
- Ca a aussi changé le contenu de "tutu". En inversant, ça change aussi le contenu de "titi". Ca a supprimé les deux fichiers.
13. Aﬀichez à l’écran le fichier/var/log/syslog. Quels raccourcis clavier permettent d’interrompre et reprendre le défilement à l’écran?
- ```CTRL + S``` permet d'arrêter le défilement et ```CTRL + Q``` permet de le reprendre.
14. Aﬀichez les 5 premières lignes du fichier/var/log/syslog, puis les 15 dernières, puis seulement leslignes 10 à 20.
- Pour afficher les 5 premières lignes : ```head -5 /var/log/syslog``` et pour afficher les 15 dernières : ```tail -15 /var/log/syslog``` .
15. Que fait la commande dmesg | less?
- La commande ```less``` permet de visualiser un fichier texte page par page.
16. Affichez à l’écran le fichier/etc/passwd; que contient-il? Quelle commande permet d’afficher la page de manuel de ce fichier?
- ```cat /etc/passwd``` permet d'afficher les utilisateurs et certains informations relatives. Pour afficher la page manuel : ```man 5 intro```
17. Affichez seulement la première colonne triée par ordre alphabétique inverse
- ```cut -d: -f1 /etc/passwd | sort -r```
18. Quelle commande nous donne le nombre d’utilisateurs ayant un compte sur cette machine (pas seule-ment les utilisateurs connectés)?
- ```cat /etc/passwd | wc``` et on a 32 utilisateurs.
19. Combien de pages de manuel comportent le mot-clé conversion dans leur description?
- ```man -k conversion | wc -l``` on obtient donc 4.
20. A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine
- ```find . -name passwd```
21. Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier~/list_passwd_files.txtet que les erreurs soient redirigées vers le fichier spécial/dev/null
- ```find . name passwd >> ~/list_passwd_files.txt 2>>/dev/null```
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

![screen Exo4Q4](/img/inviteCommande_Exo4Q4.png)
