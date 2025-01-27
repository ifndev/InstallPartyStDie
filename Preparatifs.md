 # Etapes préparatoires
 
 | [Précédent](README.md) | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | [Suivant](Installation.md) |
 | :---   | :---: |    ---: |
 
 
 ## Principe général
 À l'issue de ce tutoriel, vous aurez une clé USB sur laquelle un système linux sera installé. Afin de booter sur linux, il vous suffira de
 - éteindre votre ordinateur, 
 - insérer cette clé dans un port, 
 - rallumer l'ordinateur
 - choisir le One Time Boot (OTB) afin de choisir de booter sur la clé

 En effet, le démarrage par défaut se fait sur le disque dur. Celui-ci contiendra toujours votre système d'exploitation originel et le demarrage par défaut, san,s OTB sera donc inchangé. 
 
 La manipulation à réaliser pour activer le OTB dépend de votre ordinateur.
 - pour les ordinateurs Apple : appuyer sur la touche <tt>alt</tt> lorsque le son est émis au démarrage; une liste de disque disponibles apparaît, parmi lesquels la clé USB qu'il faut choisir
 - pour les PC, cela dépend de la marque. Le principe est cependant le même : il faut appuyer sur une touche au tout début de démarrage. Vous pouvez vous référer à [cette page web](https://www.disk-image.com/faq-bootmenu.htm) ou encore [celle-ci](https://techofide.com/blogs/boot-menu-option-keys-for-all-computers-and-laptops-updated-list-2021-techofide/) si vous ne savez pas/ne vous souvenez plus de la touche en question.

 Pour revenir à votre système d'exploitation initial, il suffit de redémarrer l'ordinateur.
 
 Il est important que vous ayez conscience que faire tourner un système d'exploitation (linux, ici) depuis une clé USB est plus lent que de la faire tourner depuis le disque dur de votre ordinateur, notamment si celui-ci est un disque SSD. L'installation de linux en dual boot (choix du système effectué systématiquement au démarrage) n'est pas plus compliqué que ce qui est décrit ici. Il faut juste faire de la place sur le disque dur, en repartitionnant celui-ci.
 
 ## Matériel nécessaire
 Pour suivre ce tutoriel vous aurez besoin de:
 - une clé USB d'au moins 32 Go : le système linux sera installé sur cette clé (voir le principe exposé ci-dessus). Cette clé pourra vous être donnée gracieusement par l'IUT lors de l'install party
 - une autre clé USB d'au moins 4 Go : cette clé contiendra l'image des fichiers d'installation. Les animateurs de l'install party en auront tout un stock à disposition, sachant que cette clé n'est plus utile une fois l'installation terminée. Vous pouvez cependant venir avec votre propre clé si vous voulez réaliser l'installation de A à Z
 - l'ordinateur sur lequel vous lancerez le linux installé sur la clé USB. Les fichiers et la configuration du système d'exploitation sont en effet très dépendants du materiel sur lequel le système s'exécute. Vous ne pourrez donc a priori pas lancer le linux installé sur la clé, à partir d'un autre ordinateur que celui sur lequel l'installation aura été faite.

## Choix du linux
Par défaut, il est proposé d'installer la version LTS (long time support) d'[Ubuntu](https://ubuntu.com). Aujourd'hui, il s'agit de la version 20.04.3 qui est [supportée jusqu'en 2025 (2030 pour les mises à jour de sécurité)](https://ubuntu.com/about/release-cycle).


La configuration matérielle recommandée pour une bonne expérience utilisateur est la suivante :
- processeur de 2 GHz dual core
- mémoire système (RAM) de 4 GiO
- espace disque de 25 Go : il s'agit ici de la clé USB sur laquelle linux sera installé
- écran compatible VGA avec une résolution minimale de 1024x768
- 2 ports USB (pour l'installation)
- accès internet

Il est possible que votre ordinateur soit plus ancien et/ou avec un matériel de puissance insuffisante, ou trop proche de la limite. Il existe des alternatives dites "lègères" à Ubuntu que vous pouvez installer. Dans ce tutoriel, nous avons choisi [Xubuntu](https://xubuntu.org) qui recommande la [configuration minimale suivante](https://xubuntu.org/requirements/) :
- processeur 1.5Ghz dual core
- mémoire système (RAM) de 2 GiO
- espace disque de 20 Go
- 2 ports USB
- accès internet

Nous ne décrivons ici que l'installation de la version 64 bits qui convient à la plupart des processeurs suffisamment récents. Des version 32 bits existent aussi, notamment pour Xubuntu.


**Les étapes suivantes ne sont pas nécessaires si vous participez à l'install party : les clés d'installation sont mises à disposition par les animateurs. Dans ce cas, vous pouvez directement passer à [l'installation](Installation.md).**

## Téléchargement et création de la clé d'installation
Si vous n'avez pas de clé d'installation, il faut d'abord télécharger une image (fichier .iso) de la clé d'installation : cette image contient tout ce qu'il faut pour installer un nouveau système.

Si vous avez choisi Ubuntu, allez sur le [site de téléchargement](https://ubuntu.com/#download) et choisissez la version Desktop 20.04 ([lien direct](https://ubuntu.com/download/desktop/thank-you?version=20.04.3&architecture=amd64))

Si vous avez choisi Xubuntu, il faut [récupérer un fichier torrent](https://xubuntu.org/download) (choisir la version LTS 20.04 64bits, voici un [lien direct](https://torrent.ubuntu.com/xubuntu/releases/focal/release/desktop/xubuntu-20.04.3-desktop-amd64.iso.torrent)). Il vous faut donc un logiciel torrent (par exemple [utorrent](https://www.utorrent.com)).

Dans les deux cas, vous aurez récupéré, a priori dans votre dossier de téléchargements, un fichier avec pour extension <tt>.iso</tt> (<tt>ubuntu-20.04.3-desktop-amd64.iso</tt> pour Ubuntu, et <tt>xubuntu-20.04.3-desktop-amd64.iso</tt> pour Xubuntu). 

L'étape suivante consiste à transférer cette image sur la clé USB d'installation. Cela va dépendre du système dont vous disposez.

### Sous PC/Linux 
Vous pouvez suivre [ces indications](https://ubuntu.com/tutorials/create-a-usb-stick-on-ubuntu#1-overview). Mais si vous avez déjà linux installé, pas besoin d'en dire plus... À noter que si vous n'avez pas l'utilitaire *Startup disk creator* (installé par défaut sous Ubuntu, mais pas sous Xubuntu par exemple), le paquet à installer est <tt>usb-create-gtk</tt> sous Gnome ou <tt>usb-creator-kde</tt> sous KDE.

### Sous PC/Windows
Vous pouvez suivre [ces indications](https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#1-overview). En voici un résumé en français:
- Installer le logiciel [Rufus](https://rufus.ie/)
- Lancer Rufus et insérer la clé USB (au moins 4Go)
- Sélectionner la clé USB dans le champ <tt>Device</tt>
- Sélectionner <tt>FreeDOS</tt> dans <tt>Boot selection</tt>
- Cliquer sur le bouton <tt>SELECT</tt> et sélectionner le fichier image <tt>ubuntu-20.04.3-desktop-amd64.iso</tt> ou <tt>xubuntu-20.04.3-desktop-amd64.iso</tt> selon le linux choisi
- Cliquer sur <tt>START</tt>
- Si une fenêtre apparaît pour avertir que des téléchargements supplémentaires sont requis (*Download required*), cliquer sur <tt>Yes</tt>
- Rufus émettra ensuite une fenêtre avertissant qu'il a détecté l'écriture d'un fichier ISO : conserver *Write in ISO Image mode* et cliquer sur <tt>OK</tt>
- Puis vous serez prévenus que toutes vos données vont être détruites sur la clé USB, cliquer sur <tt>OK</tt>
- L'écriture se lance, sa progression apparaissant dans le barre *Status*. Cela peut prendre 10 minutes.
- L'écriture est terminée quand la barre de statut est intégralement verte et contient le mot <tt>READY</tt>. Cliquer alors sur <tt>CLOSE</tt> et récupérer la clé USB.

### Sous Apple/MacOS
Vous pouvez suivre [ces indications](https://ubuntu.com/tutorials/create-a-usb-stick-on-macos#1-overview)
- Installer le logiciel [Etcher](https://etcher.io/)
- Insérer la clé USB et lancer Etcher
- *Select image* : Sélectionner l'image. C'est le fichier ISO (<tt>ubuntu-20.04.3-desktop-amd64.iso</tt> pour Ubuntu, et <tt>xubuntu-20.04.3-desktop-amd64.iso</tt> pour Xubuntu)
- *Select drive* : Sélectionner le disque. C'est la clé USB.
- *Flash!* : ne sera activé que lorsque l'image et la clé auront été sélectionnées. Cliquer sur <tt>Flash!</tt> pour lancer l'écriture. 
- Votre mot de passe administrateur est demandé puis l'écriture se déroule.
- Lorsque la mention *Flash Complete!* apparaît, le processus est terminé. Vous pouvez quitter le logiciel et récupérer votre clé USB.

Vous êtes maintenant prêts pour [l'installation](Installation.md).

## Quelques précautions d'usage…

Les manipulations avec les systèmes d'exploitation sont parfois risquées… Surtout si vous avez pris la courageuse décision de remplacer l'OS de votre ordinateur, au lieu d'utiliser la clé USB.

**FAITES. DES. BACKUPS.**

Vous avez plusieurs possibiltés pour stocker les données que vous souhaitez conserver : la clé USB qui vous aura été fournie, un cloud, etc.

| [Précédent](README.md) | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | [Suivant](Installation.md) |
 | :---   | :---: |    ---: |
