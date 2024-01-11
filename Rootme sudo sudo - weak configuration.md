This challenge is from the App-script system range. It’s entitled Sudo-Weak configuration. So as for me, you can already guess that it is about a vulnerability in the configuration of the sudo command on our machine that we’ll exploit in the other to find our flag.

J’irai à présent en français comme mon terminal que je vais d’ailleurs penser à désormais mettre en anglais.

![](Aspose.Words.929b42a3-d298-427e-ac66-55e3002602df.001.png)

Après s'être connecté via ssh à la machine contenant notre drapeau. Nous listons les fichiers et les répertoires contenus dans notre répertoire courant à l'aide de la commande ls -la.

Une fois que c'est fait, vous pouvez voir un fichier readme dans le répertoire courant, indiquant qu'un fichier .passwd est contenu dans le répertoire : /challlenge/app-script/ch1/ch1cracked Quand on liste les permissions sur le fichier, on voit que l’utilisateur app-script-ch1-cracked en est le propriétaire, mais qu’il n’a que les droits de lecture sur le fichier, donc on ne peut que le lire via des commandes comme cat, less ou more, etc.




![](Aspose.Words.929b42a3-d298-427e-ac66-55e3002602df.002.png)

J’ai alors pesné à lister les permissions de l’utilisateur app-script-ch1 pour savoir quelle commande je pouvais utiliser pour lire le fichier avec sudo -l. J’ai alors remarqué que cet utilisateur pouvait exécuter des commandes en se faisant passer pour l’utilisateur app-script-ch1-cracked notamment /bin/cat sur les fichiers du répertoire /challenge/app-script/ch1/notes/

![](Aspose.Words.929b42a3-d298-427e-ac66-55e3002602df.003.png)

La preuve, j’ai pu lire le contenu d’un fichier contenu dans le répertoire notes/

Sauf que le fichier que je veux lire est dans un répertoire adjacent à notes/ comment procéder ?

C’est alors là que j’ai eu l’idée assez ingénieuse de tenter d’accéder au répertoire ch1cracked/ depuis le répertoire notes/ ce qui d’ailleurs se fait juste en utilisant les deux points pour exécuter une commande en direction d’un dossier parent.

![](Aspose.Words.929b42a3-d298-427e-ac66-55e3002602df.004.png)

Une fois que vous y parvenez, vous avez votre flag.



