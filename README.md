# Detection-de-masques
Programme permettant la détection (ou non) de masques à travers un stream vidéo ou par une image en utilisant les librairies OpenCV, Tensorflow et Keras.


## Dataset Utilisé 
L'ensemble du DataSet utilisé est dans le dossier dataset/  et est composé de 2 sous-dossiers équilibrés : 
    - with_mask  qui contient 2165 images 
    - without_mask qui contient 1930 images.

Ces images ont été récupérés sur un DataSet public disponible sur Kaggle ou sur un dépot public git : ([Ici](https://github.com/X-zhangyang/Real-World-Masked-Face-Dataset)) 

## Prérequis 
L'ensemble des dépendances se trouvent dans le fichier : 
``` requirements.txt ``` . qui peuvent s'installer , à la racine du projet après avoir cloné le projet, avec 

>$ pip3 install -r requirements.txt

## Installation
 On peut réentrainer le modele (si ajout de nouvelles images dans le DataSet) avec 
 
 >$ python3 train_mask_detector.py --dataset dataset
 
 Ensuite, pour détecter des masques à travers une image , on fait : 
 
 >$ python3 detect_mask_image.py --image (lien vers votre image)

et Enfin , si on veut détecter des masques à travers un stream vidéo (votre caméra), on execute : 

>$ python3 detect_mask_video.py

## Resultat du Modèle

Ce modèle permet de trouver des masques avec une efficacité de 98%.
![resultat sur different scoring](https://github.com/IAAP-project/Detection-de-masques/blob/main/result/plot.png )

![resultat sur different scoring](https://github.com/IAAP-project/Detection-de-masques/blob/main/result/accuracy.png)

## Test 
Nous avons testé notre modèle sur l'un d'entre nous, lorsqu'il porte une masque : 
![Ici](https://github.com/IAAP-project/Detection-de-masques/blob/main/result/withMask.png)

Puis sans masque : 
![Ici](https://github.com/IAAP-project/Detection-de-masques/blob/main/result/withoutMask.png)

Et enfin, lorsqu'il le porte de manière non conventionnelle : 
![Ici](https://github.com/IAAP-project/Detection-de-masques/blob/main/result/withOrWithoutMask.png)

Nous avons également permis la possibilité de détecter plusieurs personnes en même temps , dans une même vidéo stream.
![Ici](https://github.com/IAAP-project/Detection-de-masques/blob/main/result/detection_mulitple.png)


## Fin du programme 
Pour quitter le programme, il suffit d'appuyer sur la touche 'd' de votre clavier pour fermer la fenêtre et arrêter l'éxecution du programme.