[Retour à la post-installation](PostIntallation.md)

## Windows se lance directement
- au redémarrage, appuyez vite sur la touche qui fait apparaître le *Boot Menu* 
  - Choisissez l'option de boot qui correspond à linux
  - Si linux se lance bien, le problème était sans doute lié au fait que le démarrage depuis le disque dur était prioritaire sur le démarrage depuis la clé USB. Lors du prochain démarrage, il faudra revenir dans le BIOS et changer l'ordre de priorité des *Boot options* afin que la clé USB vienne en premier
 
 
## J'ai un écran noir avec <tt>grub ></tt>
- l'installation du bootload a échoué.

A TERMINER
- Choisissez *Ubuntu* dans le menu
- Connectez-vous avec le mot de passe indiqué lors de l'installation pour l'utilisateur
- Ouvrez firefox et récupérez ce fichier [https://github.com/ekerrien/InstallPartyStDie/blob/main/postInstall.sh](postInstall.sh)
- Ouvrez un terminal
  -  sous Ubuntu: touche Windows, puis entreé *term* dans le champ de recherche. Cliquez sur le terminal
  -  sous Xubuntu: menu (icone avec une tête de souris blanche sur fond bleu, en haut à gauche), puis *Favoris*, puis *Emulateur de terminal*
- Dans le terminal, tapez les commandes suivantes :
  - <tt>sudo chmod 755 ~/Téléchargements/postInstall.sh</tt> (indiquez votre mot de passe)
  - <tt>sudo ~/Téléchargements/postInstall.sh</tt>
- Redémarrez l'ordinateur en appuyant sur la touche d'arrêt qui vous propose un menu de redémarrage
    - Si ce n'est pas le cas (Windows se lance alors que la clé est insérée) : allez dans le menu du BIOS et changer l'ordre de options de boot, en mettant la partition 1 de la clé USB en premier
    - Une alternative, si la touche de lancement du *Boot menu* fonctionne bien, alors vous pouvez l'utiliser lorsque vous souhaitez lancer linux (même fonctionnement que pour MacOS)

[Retour à la post-installation](PostIntallation.md)
