This challenge is also from the App-script system range. It’s the Bash System 2. To solve it, the tip is to use the weak configuration of permissions on repositories and command on our machine that we’ll exploit in the other to find our flag.

J’irai à présent en français comme mon terminal que je vais d’ailleurs penser à désormais mettre en anglais. Pour cause, il est toujours en français.

![](Aspose.Words.1e962622-def7-4b7e-bda4-5eeb0bb18469.001.png)

Après s'être connecté via ssh à la machine contenant notre drapeau. Nous listons les fichiers et les répertoires contenus dans notre répertoire courant à l'aide de la commande ls -la.

Une fois que c'est fait, vous pouvez voir un fichier ch12.c dans le répertoire courant, contenant des instructions pour lister l’emplacement et les droits sur un fichier et indiquant que le fichier .passwd est contenu dans le répertoire : /challlenge/app-script/ch12/ . Quand on liste les permissions sur le fichier, on voit que l’utilisateur app-script-ch12-cracked en est le propriétaire, mais qu’il n’a que les droits de lecture sur le fichier, donc on ne peut que le lire via des commandes comme cat, less ou more, etc essentiellement pareil au challenge passé.


![](Aspose.Words.1e962622-def7-4b7e-bda4-5eeb0bb18469.002.png)

Comme vous pouvez le voir, j'ai alors pensé à créer un lien symbolique vers le fichier /bin/cat pour exécuter cat à la place de ls ce qui n’était en soi pas possible parce que la commande cat ne dispose pas de l’option -lA qui était utilisé dans le fichier ch12.c. Après quelques recherches, je me suis penché sur l’utilisation de la commande nano qui n’est pas sensible à la casse lorsque la commande exécutée comprend une option non disponible.

Mais la création du lien symbolique nécessite des droits qui n’étaient pas attribués sur le répertoire courant. Permission denied error !!

Alors vient la question d’observation, si vous faites bien attention, vous verrai que juste après la connexion au shell, il y a une ligne qui vous indique que les répertoires /tmp et /tmp/var sont writeables pour dire que vous avez les droits d’écriture sur ces répertoires. En ce rendant dans le répertoire  /tmp on parvient donc à  changer le path après avoir créer le lien symbolique.

![](Aspose.Words.1e962622-def7-4b7e-bda4-5eeb0bb18469.003.png)

Une fois que c’est fait il suffit d’exécuter le ficher ch12 dans le répertoire  /tmp pour lire le contenu du fichier .passwd

![](Aspose.Words.1e962622-def7-4b7e-bda4-5eeb0bb18469.004.png)

Une fois que vous y parvenez, vous avez votre flag.



