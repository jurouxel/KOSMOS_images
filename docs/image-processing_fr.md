# Traitement des vidéos issues du système KOSMOS <img width="50" alt="image kosmos" src="https://user-images.githubusercontent.com/108416242/182578775-55f881ab-6064-4b50-8c58-42cfca3f6113.PNG">


Le but de cet algorithme est d'améliorer les vidéos sous-marines en traitant la turbidité et en corrigeant les couleurs (en python) 

## I/ Prérequis 

### 1. Logiciels nécéssaires 
 - Installer Python3 sur Linux ou windows
   - [Sur Linux](https://doc.ubuntu-fr.org/python) ```sudo apt install python3```
 - Installer PIP
   - Sur Linux ```sudo apt install pip```
 - Installer Spyder
   - [Sur Linux](https://doc.ubuntu-fr.org/spyder) ```sudo apt install spyder```

### 2. Installation des librairies pythons
 - Sur Python, installer les librairies suivantes :  
   - OpenCV-python
   - Numpy
   - Math-python
   - moviepy
   - Pathlib
   - Imageio 
   - OS (n'existe pas)
   - multiprocessing (Erreur installation)
   - concurrent.futures (Introuvable)

Pour installer les librairies, tapez dans la console spyder : ```conda install OpenCV-python```
Ou dans le cas où conda n'est pas installé, on peut via un terminal Linux entrer (exemple avec OpeCV-python) ```pip install OpenCV-Python```

### 3. Préparation de l'espace de travail
Préparer dans les dossiers une arborescence semblable à celle-ci : <img width="700" height = "100" alt="image" src="https://user-images.githubusercontent.com/108416242/185398078-308eef6c-1bec-4154-a7a8-23f91d2af5e1.PNG">

Placer les vidéos à traiter dans le dossier "Videos", le script s'occupera de placer les vidéos traitées dans le dossier "Videos traitées". Le dossier "Frames" quand à lui contiendra toutes les images des videos, ces images seront traitées directement dans ce dossier. 

/!\ Pensez à vérifier que les chemins des différents dossiers, présents dans le code, sont exacts.

- Processing.py : contient le code qui va traiter une vidéo/image avec les méthodes d’égalisation d’histogramme, de débrumage et le rétinex. [Il s'agit du script que l'on peut trouver dans le présent dépot](https://github.com/jurouxel/KOSMOS_images/blob/main/Image_processing/processing.py) 


## II/ Lancer l'algorithme 

### 1. Renseigner les paramètres 
Dans le script processing.py il y a une partie déstiné à renseigner certains paramètres (ligne 335 à 351): 

``` 
### PARAMETRES A RENSEIGNER ### 
filename_video = './Vidéos/kosmos_2022-07-19-19-09-16.mp4'

db_min = 13
db_s =44

fin_min = 13
fin_s= 54

method = "HE"

filename_video_a_traiter = "./Vidéos/video.mp4"
###############################
```
 - **filename_video** : Chemin de la vidéo qui devra être traitée. 
 - **db_min, db_s, fin_min, fin_s** : Est destiné à renseigner la durée de la vidéo que l'on souhaite traiter avec un temps de début (db) et de fin (fin). On notera la valeur de minutes (min) et de secondes (s) sépéréments. *Il est également possible de ne traiter qu'une frame en définissant fin_min et fin_s à 0.* 
 - **method** : Est la variable qui indique quelle méthode de traitement on souhaite utiliser, il est possible de rentrer soit "HE", "retinex" ou "UDCP".
 - **filename_video_a_traiter** : Chemin de dépôt de la vidéos après traitement. C'est ici que l'on nomera le fichier de sortie. Ne pas hésiter à écrire la méthode utilisé dans le nom du fichier. 


### 2. Executer le script
 - Dans Spyder, il est possible de lancer le script en cliquant sur le triangle vert "exécution" situé dans la barre des outils.
 - /!\ Ce processus peut prendre de longues heures. Il est recommandé de l'éxecuter avec un ordinateur disposant d'une bonne puissance de calcul. 


## III/ Exemples d'une image traitée avec les deux méthodes

Image originale: 

![IP3-1.png](pictures/Image_processing/IP3-1.png) 


Image traitée avec HE et le débrumage : 

![IP3-2.png](pictures/Image_processing/IP3-2.png) 


Image traitée avec le rétinex : 

![IP3-3.jpg](pictures/Image_processing/IP3-3.jpg) 



## Sources : Algorithmes/articles utilisés :
- [Single Image Haze Removal Using Dark Channel Prior, Kaiming He, Jian Sun, and Xiaoou Tang", in CVPR 2009](http://kaiminghe.com/publications/cvpr09.pdf)
- [Guided Image Filtering, Kaiming He, Jian Sun, and Xiaoou Tang", in ECCV 2010.](http://kaiminghe.com/publications/eccv10guidedfilter.pdf)
- [Properties and Performance of a Center/Surround Retinex, Daniel J. Jobson, Zia-ur Rahman, 1997](https://pubmed.ncbi.nlm.nih.gov/18282940/)
- [A Retinex-Based Enhancing Approach for Single Underwater Image, Xueyang Fu, Peixian Zhuang, Yue Huang, Yinghao Liao, Xiao-Ping Zhang, Xinghao Ding, 2014](https://ieeexplore.ieee.org/document/7025927)


## Auteur 

***Zoë DAHERON*** - *stage technique* - IFREMER


Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sub license, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NON INFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

