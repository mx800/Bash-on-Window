

#### Installation de Bash sur window
https://www.lifewire.com/install-bash-on-windows-10-4101773
- Activer les paramètre développeur
Settings -> update and security -> For developpers > Developper mode

- Ajouter la fonctionnalité Linux
Fonctionnalité window -> Windows Subsystem For Linux

- Installer Bash
Window Strore -> Unbuntu

___
#### Installation de Cmder
https://cmder.net/

___

#### Création d'un shortcut de Cmder
https://gist.github.com/jojobyte/66c8346ed8948b9b395f

- Créer un fichier .reg pour ajouter les clées dans le registre
(Remplacer le path par la destination de Cmder)

___

#### Starup de bash par default dans Cmder
L'objectif est de créer une terminal bash ainsi que de le mettre comme terminal par defaut sur window
- Dans les option de cmder, aller sur Starup -> task
- Créer un nouveau terminal avec le + et donner lui un nom (Ex: _`bash::ubuntu`_)
- Dans la zone text area, inscrivez: ` %windir%\system32\bash.exe`
- Cocher les case "Default task for new console" ainsi que "Default shell (Win + x)"
- Aller directement sur l'onglet `Startup` à gauche et spécifier le terminal que vous venez de créer par default
___

#### Configuration de base dans Ubuntu
https://evdokimovm.github.io/windows/zsh/shell/syntax/highlighting/ohmyzsh/hyper/terminal/2017/02/24/how-to-install-zsh-and-oh-my-zsh-on-windows-10.html

Installation de CURL
```
sudo apt-get install curl
```

Installation de Zsh
```
sudo apt-get install zsh
```

Installation de Oh my Zsh
```
curl -L https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh | bash
```

Ajouter `bash -c zsh` dans le haut du document `.bashrc` pour ouvrir par default `Zsh`
```
nano ~/.bashrc

#Ajouter en haut:
bash -c zsh
```

Éviter que Unbuntu nous redemande le password pour sudo
```
sudo nano etc/sudoers

Ajouter:
#Représente 300min donc 5h
Defaults timestamp_timeout=300
```

___


#### Création d'une variable pour le HOME directory de window
L'objectif est de racourcir le path par defautl pour window. De base le `~` représente le HOME du user de Ubuntu.
Donc je crée une variable nommé `$u` dans le fichier `.profile`
```bash
nano ~/.profile

#Insérer à la fin du fichier:
export u="/mnt/c/Users/nom-utilisateur"

#Reloader les config:
source ~/.profile
```
En inscrivant `$u` vous accèderé à votre path home de l'usagé window.
Exemple:
```bash
cd $u
```
___

#### Si vous utilisez les produits JetBrains
Il est possible de changer le terminal par defaut de JetBrain pour celui de bash. Simplement faire ceci:
- Accèder au menu des settings (Shift 2x et inscrire settings)
- Dans `Terminal`. Inscrire le `Shell Path`: `C:\Windows\System32\bash.exe`
___




## Voilà! Vous êtes configuré
