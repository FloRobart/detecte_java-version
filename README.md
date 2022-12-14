# Script permettant de détecter la version de Java
Permet de savoir si **Java** est installé sur l'ordinateur sur lequel ce script est lancé.
Si Java est installée, mais n'a pas la bonne version, le script affiche une boite de dialogue permettant de télécharger automatiquement Java jdk 16.

1. Lancement du script
    * Interface graphique Windows
    * Terminal Windows
2. Modification du script
    * Changer les versions valides
    * Changer le lien de téléchargement
3. Version Linux
 

## 1. Lancement du script
Pour lancer le script, il existe deux solutions, la première via l'interface Windows et la deuxième via un terminal. Il n'y a aucune réelle différence entre les deux méthodes si ce n'est que c'est plus rapide de passer par l'interface Windows.

### Interface graphique Windows
Après l'avoir téléchargé double-cliquer sur le script.

### Terminal Windows
Après avoir téléchargé le script, ouvrez le gestionnaire de fichier dans le répertoire où se trouve se dernier puis écrivez dans la barre en haut **CMD** ou **PowerShell**.

Illustration pour ouvrir un CMD ou un PowerShell
![](./img/cmd.png "Illustration pour ouvrir un CMD ou un PowerShell")

Si vous ouvrez PowerShell écrivez `./VerifJavaVersion.bat` dans ce dernier. Si vous ouvrez un CMD écrivez `VerifJavaVersion.bat`

## 2. Modification du script
### Changer les versions valides
Si vous voulez changer les versions de java valide, il vous faut remplacer les nombres `"16 17 18 19"` à la ligne 11 par les versions de java valide dans votre cas d'utilisation.

Extrait de la ligne 11 :
```bat
FOR /F "usebackq delims=" %%A IN (`java -version 2^>^&1`) DO echo %%A | findstr /i "16 17 18 19" && (
```


### Changer le lien de téléchargement
Si vous voulez changer la version de Java installée en cas d'absence de Java ou de version de Java non-valide, il faut changer le lien après `start` à la ligne 38.

Extrait de la ligne 38 :
```bat
echo start https://www.techspot.com/downloads/downloadnow/7407/?evp=bb667956a140a1a0a56260d7df5d40bf^^^&file=9975 >> installationJava16.bat
```

**◬ Attention** même dans une URL les caractères spéciaux doivent échapper avec le caractère d'échappement approprié !


## 3. Version Linux
Si vous voulez la version **Shell** de ce programme, je vous invite à aller voir [la repos de mon collègue Hugo](https://github.com/VicenteHugo/Verification-Version-Java-Linux "Verification-Version-Java-Linux") qui a traduit mon programme **Batch** en **Shell**.
