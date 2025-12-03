# Outils


# Comment installer Oh My Zsh

Oh my zsh est environnement de bash open-source plutot ergonomique et personnalisable Ã  l'envie.

## site source
https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH

### 1er etape Verifier git
````
git --version
````
mettre a jours au besoin sinon
````
apt install git-all
````
### 2eme etape installer zsh
````
apt install zsh
````
### 3eme etape installer oh my zsh via wget
````
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
````

## Maintenant il faut copier la config Oh my Zsh du Root sur l'utilisateur (methode chatGPT)

Câ€™est la mÃ©thode la plus propre.

### 1. Depuis root, copie le dossier Oh My Zsh :
````
cp -r /root/.oh-my-zsh /home/<ton_user>/
chown -R <ton_user>:<ton_user> /home/<ton_user>/.oh-my-zsh
````
### 2. Copie aussi le fichier .zshrc du root :
````
cp /root/.zshrc /home/<ton_user>/
chown <ton_user>:<ton_user> /home/<ton_user>/.zshrc
````
### 3. Mets Ã  jour la variable ZSH dans le .zshrc du user

Ouvre :
````
nano /home/<ton_user>/.zshrc
````

Modifie (si besoin):
````
ZSH=/root/.oh-my-zsh
````

en :
````
ZSH=/home/<ton_user>/.oh-my-zsh
````
### 4. Recharge Zsh :
````
su - <ton_user>
zsh
````