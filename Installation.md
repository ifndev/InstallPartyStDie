| [Précédent](Preparatifs.md) | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | [Suivant](PostInstallation.md) |
 | :---   | :---: |    ---: |

# Installation

Installer linux est simple et rapide, une fois que vous vous êtes [bien préparés](Preparatifs.md). Il suffit de suivre ces étapes:
- Eteignez votre ordinateur
- Insérez la clé USB d'installation, ainsi que la clé USB sur laquelle vous souhaitez installer linux
- Allumez votre ordinateur en *One Time Boot* en passant par le *Boot menu*. La manipulation pour activer ce menu au démarrage dépend de votre machine.
  - Si vous êtes sur PC
    - dès le lancement (en général dès que le logo apparaît), appuyez sur la bonne touche. Pour connaître la touche en fonction de la marque de votre PC, vous pouvez vous référer à [cette page](https://www.disk-image.com/faq-bootmenu.htm) ou bien [celle-ci](https://techofide.com/blogs/boot-menu-option-keys-for-all-computers-and-laptops-updated-list-2021-techofide/). Dans de nombreux cas, la touche en question est indiquée brièvement dans un message à l'écran.
    - Une liste de disques disponibles pour le démarrage est affichée. Sélectionnez la clé USB contenant le support d'installation avec les flèches puis <tt>Entrée</tt>
    - En cas de souci, vous pouvez vous référer à [cette page](AlternateBootMenu.md)
  
  - Si vous êtes sur Apple
    - maintenez appuyée la touche <tt>alt</tt> dès que vous entendez le son du démarrage.
    - Une liste de disques apparaît : cliquez sur EFI Boot
    - Il peut y avoir deux EFI Boot : sélectionnez le premier (les deux fonctionnent pareil...)
    
    
- Un menu apparaît : 
  - Si vous avez choisi **Ubuntu** : attendez
  - Si vous avez choisi **Xubuntu** : sélectionnez (avec les flèches) *Install Xubuntu* (Vous pouvez aussi choisir dans un premier temps *Try Xubuntu without installing* pour simplement tester Xubuntu, sans impact sur votre système, et vous assurer que tout fonctionne correctement).
- (X)Ubuntu se lance... soyez un peu patient
- **Langue**: Une fenêtre apparaît : sélectionnez le français comme langue (ou celle qui vous convient le mieux), puis cliquez sur <tt>Installer Ubuntu</tt> (<tt>Continue</tt> dans le cas de Xubuntu)
- **Clavier**: Vous devez valider ensuite la disposition du clavier. En général, il est bien détecté : cliquez sur <tt>Continuer</tt> (en cas de doute vous pouvez faire quelque tests dans le champ vide juste au-dessus du bouton <tt>Détecter la disposition du clavier</tt>)
- **Réseau**: Choisissez de vous connecter au réseau de l'IUT. Entrez les informations de connexion et cliquez sur <tt>Continuer</tt>.
- **Mises à jour et autres logiciels**: ne changez rien, sauf si vous avez une carte graphique NVidia
  - En cas de carte graphique Nvidia, sélectionnez *Installer les logiciels tiers...*
  - Entrez un mot de passe: vous aurez besoin d'un mot de passe plus tard (voir **Qui êtes-vous ?** ci-dessous), vous pouvez prendre le même.
- **Type d'installation**: Sélectionnez *Autre chose*, puis cliquez sur <tt>Continuer</tt>
- **Type d'installation** (suite): 
  - Dans la liste des périphériques, choisissez la clé USB. Elle apparaît avec un nom du genre <tt>/dev/sdb</tt> (ou <tt>/dev/sdc</tt>, ou <tt>/dev/sda</tt>... on supposera ici que c'est sdb). En cas de doute, vérifier la taille des partitions qu'elle contient (en général une seule, qui doit faire environ 128Go avec les clés fournies par l'IUT).
  - Les partitions sur la clé apparaissent avec un chiffre supplémentaire (par exemple <tt>/dev/sdb1</tt>). Cliquez sucessivement sur chaque partition contenue sur la clé et supprimez-la en cliquant sur le signe <tt>-</tt> au-dessous. Faites cela jusque à ce que la seule chose présente sous la clé soit *espace libre*.
  - Sélectionnez le périphérique correspondant à la clé (ici <tt>/dev/sdb</tt>) et cliquez sur <tt>Nouvelle table de partition</tt>
  - Puis, dans l'espace libre, créez trois partitions:
    - Sous <tt>/dev/sda</tt>, sélectionnez *espace libre* et cliquez sur le signe <tt>+</tt> en-dessous. Cela ouvre une fenêtre.
    - **Taille**: 128Mo
    - **Utiliser comme**: *Partition système EFI*
    - Cliquez sur <tt>OK</tt>
    - Sous <tt>/dev/sda</tt>, sélectionnez *espace libre* et cliquez sur le signe <tt>+</tt> en-dessous. Cela ouvre une fenêtre.
    - **Taille**: 8192 Mo (4096 Mo si 2Go de RAM)
    - **Utiliser comme**: *espace d'échange (swap)*
    - Cliquez sur <tt>OK</tt>
    - Sous <tt>/dev/sda</tt>, sélectionnez *espace libre* et cliquez sur le signe <tt>+</tt> en-dessous. Cela ouvre une fenêtre.
    - **Taille**: ne changez rien (prend tout ce qui reste)
    - **Utiliser comme**: gardez *système de fichier journalisé ext4*
    - **Point de montage**: / (barre oblique)
    - Cliquez sur <tt>OK</tt>
  - Revenez à la liste des périphériques et sélectionnez la dernière partition que vous venez de créer (par exemple <tt>/dev/sda3</tt> qui est de type <tt>ext4</tt>)
  - Dans la liste *Périphérique où sera installé le programme de démarrage* sélectionnez la partition de type efi (<tt>/dev/sda1</tt> par exemple)
  - Cliquez sur <tt>Installer maintenant</tt>
  - Un message d'avertissement apparaît : cliquez sur <tt>Continuer</tt>
- **Où êtes-vous ?**: vérifiez que la zone est bien Paris, et cliquez sur <tt>Continuer</tt>
- **Qui êtes-vous ?**: 
  - Votre nom: Votre nom complet (par exemple *Erwan Kerrien*)
  - Le nom de votre ordinateur : si celui indiqué par défaut vous déplaît, vous pouvez en choisir un autre (pas d'espace et évitez les caractères spéciaux. Il y a une validation de toute façon. Essayez de choisir un truc auquel peu de gens penseront pour éviter d'avoir pleins d'ordinateurs avec le même nom sur le réseau)
  - Choisir un nom d'utilisateur : par défaut, le premier mot de votre nom, sans majuscule. Vous pouvez le changer.
  - Choisir un mot de passe : à vous de choisir. Prenez-en un suffisamment complexe quand même.
  - Confirmez votre de mot passe : ben oui, faites-le, juste pour être sûr qu'il n'y a pas d'erreur de frappe...
  - Pour des raisons de sécurité, il est fortement recommandé de sélectionner *Demande mon mot de passe pour ouvrir une session*
- L'installation se lance. Soyez patients...
- Une fois l'installation terminée, il vous est demandé de redémarrer. Cliquez sur <tt>Redémarrez maintenant</tt>
- À un moment, il vous sera demandé de retirer la clé d'installation. Après l'avoir fait, vous pourrez continuer le redémarrage en appuyant sur la touche <tt>Entrée</tt>
- Vous n'avez plus besoin de la clé d'installation et vous pouvez la rendre pour que le ou la suivante puisse s'ouvrir aux bienfaits de linux !


La suite du redémarrage est expliquée dans la [post-installation](PostInstallation.md)


| [Précédent](Preparatifs.md) | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | [Suivant](PostInstallation.md) |
 | :---   | :---: |    ---: |
