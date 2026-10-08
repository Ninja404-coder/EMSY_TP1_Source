# TP1 - Installation Linux sur une VM - V0.4

## Groupe 
Gabriel (GOM) 	- Nikola (NDC)

## But 

Cette manipulation a pour but d'installer une distribution linux [Sparky Linux](https://sparkylinux.org/) dans une machine virtuelle VMware 
Workstation Player, à l’aide d’une image disque (ISO).

## Materiels à disposition 

- VMware Workstation Player - V17
- Image disque (ISO) : sparkylinux-6.4-x86_64-minimalcli.iso

## Création d’une machine virtuelle 

**A.** Lancez VMware Workstation Player (logiciel)  

**B.** Sélectionnez **Create a New Virtual Machine** 

**C-A.** Placez le fichier `.iso` dans une repertoire connu : 

`C:\VosInitiales\VM\ISO`

**C-B.** Indiquez le chemin d’accès de l’image iso comme indiqué sous l’image ci-dessous :

![install image disk](/Images/Install_ISO.jpg) 

**D-A.** Choisissez un nom d'OS : `Linux - Debian 11.x` 

![OS name choice](Images/OS_Choice.jpg) 

**D-B.** Nommez la machine virtuelle : `SparkyLinux-VosInitiales` 

**E.** Creez un disque virtuel -> capcité : **20GB** 

> Remarque 1 : Cocher **store virtual disk a single file**

![Virtual disk](/Images/VirtualDisk.jpg) 

> Remarque 2 : Ci-dessous, la configuration de la VM 

![Virtual disk](/Images/VM_Config.jpg) 

**F.** Lancez la machine virtuelle : **Play virtual machine** 

## Lancement de l'image ISO (Linux - Live CD) 

**G.** Lancement du live CD : 

<img width="636" height="292" alt="image" src="https://github.com/user-attachments/assets/40ca6875-a661-4b97-a004-ca1761e92f9a" />



Shell Linux : 

[Placer votre capture d'écran]() 

> **ATTENTION** : par défaut, le clavier est configuré est **Clavier Americain**

Q1. disposition du clavier américain ?

> QWERTY

Q2. disposition du clavier suisse-romand ?

> QWERTZ

Q3. disposition du le clavier français ? 

> AZERTY

**H.** Déplacez-vous à la **racine du système** en utilisant la commande suivante : `cd` 

Q4. cd /

**I.** Affichez le contenu de la racine avec la commande : `ls –l`	

<img width="716" height="390" alt="Capture ls -l" src="https://github.com/user-attachments/assets/d46ed638-22a6-4f67-8f07-66934e78e9f0" />


Q5. Que signifie l'option `-l` avec la commande `ls` 

L'option de commande -l permet d'afficher des informations détaillées sur le contenu du répertoire dans un format en colonnes qui inclut la taille, la date et l'heure de modification, le nom du fichier ou du répertoire, le propriétaire du fichier et ses permissions.

Q6. Décrypter la ligne où se trouve le répertoire **home**    

<img width="456" height="22" alt="Capture d&#39;écran 2026-09-24 150615" src="https://github.com/user-attachments/assets/b79b8d9b-90fb-4de6-a166-00b4763bdc18" />

> drwxr-xr-x : Les permissions séparé en trois partie. D'abord le propriétaire (rwx), ensuite le groupe (r-x) et enfin autre utilisateur (r-x)
>
> d : signifie répertoire (directory)
> 
> 1 : Le contenu du répertoire
> 
> root root : Le propriétaire
> 
> 60 : La taille de modification
> 
> Sep 24 : La date de modification
> 
> 13:03 : L'heure de modification

**J.** Créez un répertoire de travail nommé « EMSY_VosInitiales» 

Q7. dans quel dossier racine allez-vous le placer (justifiez votre réponse) 

> Il faut placer le dossier dans répertoire de l'utilisateur courant (live)
> <img width="264" height="65" alt="Capture d&#39;écran 2026-09-24 155031" src="https://github.com/user-attachments/assets/03788960-6627-4d21-bf59-f10f7eca63eb" />


Q8. Quelle commande allez-vous utiliser pour faire ceci ?  

> mkdir EMSY_GMO_NDC

**K.** Dans ce répertoire, créez un fichier texte que vous nommerez `TESTSLO_XXX_XXX` et éditez celui en écrivant un texte, exemple : "TP linux by XXX et XXX".
	   Utiliser la commande `vi`

> touch TESTSLO_GMO_NDC

Q9. Pouvez-vous éditez un fichier uniquement avec la commande `vi` 

> non, il y a la commande nano.

Q10. Si vous éteignez la machine virtuelle et que vous la rallumez, est-ce que le répertoire créé ci-dessus existe toujours (justifiez votre réponse) ? 

> non, parceque on a créé le répertoire dans un cd-live qui ne s'enregistre pas.

**L.** Tapez la commande `ls -l /dev/sda` 

<img width="399" height="19" alt="Capture d&#39;écran 2026-09-29 142251" src="https://github.com/user-attachments/assets/86a79401-9594-4d75-87bf-ab50f8f8b531" />

Q11. Que signifie **sda** ? 

> le dossier "sda" correspond un pilote de périphérique du dossier "dev". celui ci correspond un disque dur associé pour la vm. 

Q12. Quelle différence y a-t-il entre le répertoire de la question Q6 et celui du point L (justifiez votre réponse) ?

> Le répertoire de la Q6 est le dossier home qui contient les répertoire personnel de chaque utilisateurs.
> Le répertoire présenté ici est le dossier dev qui les pseudo fichier ou "devices" associés aux pilotes de phériphérique.

## Installation de SparkyLinux sur la VM

**M.** Installez SparkyLinux

![Placer vos captures d'écrans de l'installation]()

Q13. Quelle est la taille de disque minimum recommandée pour installer la distribution Sparky en mode cli 

> 2Go

Q14. A quoi sert la partition swap ? Est-ce que ce principe existe-t-il sur les OS Microsoft Windows ? 

> La partition swap permet au système d'exploitation de déplacer temporairement des données de la RAM vers le disque afin de libérer de la mémoire. Oui. 

Q15. Quel format pourriez-vous utiliser pour la 3ème partition afin qu’elle soit également accessible depuis un OS Microsoft ? 

>Le format qu'on peut utiliser qu'il est accessible depuis un OS Microsoft est le FAT32.

Q16. Durant l’installation, on vous demande deux noms d’utilisateur. A quoi correspondent-ils ? 

> Le premier correspond au nom du compte administrateur et le deuxième nom correspond au nom du compte standard

**N.** Une fois l’installation de Linux terminée, prenez une capture d’écran du démarrage de votre système (GRUB)

<img width="621" height="420" alt="Capture d&#39;écran 2026-10-07 142856" src="https://github.com/user-attachments/assets/cbb85de5-6302-4822-9a56-80f2f531ca28" />

**O.** Trouvez la ou les lignes de commande permettant de changer le clavier et procédez à la configuiration 

> sudo dpkg-reconfigure keyboard-configuration

<img width="820" height="622" alt="SparkyLinux changement language clavier" src="https://github.com/user-attachments/assets/175c3ebb-fd5d-49e5-9e6f-6ca7100a9b7d" />


**P.** Tapez la commande : `nano -version`

<img width="498" height="112" alt="SparkyLinux code nano" src="https://github.com/user-attachments/assets/01ff5ce4-a8cf-4cfd-8168-c9a266171888" />

Q17. A quoi sert `nano` ? 

> nano est un éditeur de texte en ligne de commande qui fonctionne directement dans le terminal.

**Q.** Testez si l’application `git` est installée sur votre distribution, si ce n’est pas le cas installez un client git. 

Q18. Comment savoir si `git` est déjà installé ? 

> On peut le savoir si on tape "git" ou "git --version". Si une version s'affiche, git est déjà installé sur la machine. Sinon, si un message d'erreur s'affiche ou que le programme n'est pas trouvé, il faut l'installer.

git --version

Q19. Si le client `git` n'est pas installé, quelle(s) commande(s) utilisez-vous pour l’installer ? 

> On utilisera sudo apt install git ou sudo apt-get git

Q20. Que veut dire `apt` ? 

> apt veut dire Advanced Packaging Tool

Q21. Est-ce que cette commande (`apt`) peut être utilisée sur toutes les distributions Linux (justifiez votre réponse)? 

Non. cdLa commande "apt" peut être utiliser sur Debian et Ubuntu seulement.

**R.** Créez un sous-répertoire « EMSY_TP1_XXX-YYY » dans le répertoire de votre utilisateur. 
       
**Attention** : Ici on veut que l’utilisateur (vous) ait les droits de lecture, d’écriture et d’exécution.

mkdir EMSY_TP1_NDC_GOM

Q22. Quel est le répertoire utilisateur ?  

gabmouraoli (Nom défini par GMO depuis l'installation)
banane (Nom défini par NDC depuis l'installation)

Q23. Quelles sont les commandes pour changer les droits d'utilisateurs (lecture - écriture - execution) ?  

> chmod u-rwx
> chmod u+rwx

**S.** Dans ce répertoire, tapez la commande : `git clone https://github.com/votreDepot/EMSY_TP1_Source`

***Remarque*** : Il faut au préalable que vous ayez mis en place à cette adresse un fork du dépôt fourni lors de ce TP.

Q24. Qu’observez-vous dans ce répertoire ?

<img width="812" height="187" alt="Clone git" src="https://github.com/user-attachments/assets/adaa0b6d-ba98-4e70-9dc4-ade843bb2516" />


**T.** Editez le fichier source `.c` avec l’éditeur de texte « nano ». -> Réalisez un petit programme en C (par exemple de type « Hello world »).

<img width="800" height="539" alt="Capture d&#39;écran 2026-10-08 085207" src="https://github.com/user-attachments/assets/2562f4de-7163-422b-8d69-958509221d0a" />

**U.**	Vérifiez si le compilateur `gcc` est bien installé. Notez la version du logiciel

<img width="608" height="90" alt="Capture d&#39;écran 2026-10-08 085510" src="https://github.com/user-attachments/assets/3fe1861a-97bf-485d-9598-32d0b0497ea4" />


**U-A.** Tapez les commandes suivantes :
```Shell 
gcc -Wall -o fichier.o -c fichier.c 
gcc -o fichier fichier.o 
```
Remarque : « fichier » est à remplacer par le nom de votre choix


Q25. Quels sont les fichiers qui ont été générés 

Ce qui à été généré est le fichier EMSY_TP1.o

<img width="812" height="187" alt="Clone git" src="https://github.com/user-attachments/assets/30cf7823-9628-488f-ba5b-d0cf0c2776de" />


**V.** Entrez la commande suivante : `./fichier`

<img width="616" height="99" alt="Execution de EMSY TP1_fichier" src="https://github.com/user-attachments/assets/e64cb181-d8fa-44dc-822c-808cd18b4710" />


Q26. Que se passe-t-il ?

On a éxécuté le programme qu'on a généré. Il a un message qui affiche "Hello World"

## Tips 

> Tip 1 : sortir de la VM -> appuyer simultanément sur `Ctrl` et `Alt` 

> Tip 2 :  
> Pour arrêter un Linux proprement : 	`shutdown`  
> Pour forcer l’arrêt d’un système :	`halt` ou `poweroff`  
> Seul un administrateur peut exécuter ces commandes !

> Tip 3 : [commande vi avec ses options](https://www.linuxtricks.fr/wiki/guide-de-sur-vi-utilisation-de-vi)

> Tip 4 : [éditer un fichier type markdown (.md)](https://ashki23.github.io/markdown-latex.html)

