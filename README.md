## IA LAB : SELF DRIVING CAR

# Introduction 
Actuellement, il y a un nombre croissante sur l'utilisation de l' IA. l'intélligence artificielle permet de doter à un ordinateur la capacité de faire des tâches comparable à un être humain. Pour cette laboratoire , on va imiter le conducteur tout en minimisant le nombre d'erreur possible.


# Développement 
# Donnée dans le fichier .csv:
- Image de gauche
- Image du centre
- Image de droite
- Angle de braquage
- Accélération
- Sens inverse
- Vitesse

# fonctionnement 
- Entrée : 3 captures d’images de l'avant de la voiture ( gauche , centre, droite )
- Sortie : angle de braquage

# Technique d'apprentissage utilisé
## CNN: Conventional Neural Network
C’est une technique d'apprentissage supervisé. On reçoit les images en entrée et on prédit l’angle de braquage. Il faut noté que la raison de CNN est que c'est destiné au traitement d'image. c'est pour cette raison qu'on a choisit cette technique. Au tout , début on va traiter les images pour ne garder que les essentielles avant de les faire passer à travers le réseau.
Le premier réseau de neurone applique les opérations de filtrages avec plusieurs noyaux de convolutions, puis redimensionne . L'objectif est de traiter les images et d’extraire les informations importantes. On passe les données d'entrainement à travers les réseau de convolution . On applique le technique de Pooling, qui signifie de ne garder que les données nécessaires . On utilise aussi le dropout , qui permet de désactiver certain neurone. Puis, on fa utiliser flatten permettant de créer le vecteur final au réseau de neurone. Le second réseau de neuron permet de prédire l’angle de braquage en fonction des information issus des réseaux de neurones précédentes. Après, les divers couches de neuronnes subit plusieurs optimization par gradiant descent.

## Mise en place: 
80 %  des donnée des données sont d'entraînement 

20 % des données sont pour le test.

## Phase d'entrainement :
On va faire deux entrainement : l'autre l'utilisation de CPU et l'autre utilisation de GPU .
Pour le cas de CPU : on utilise juste 3 couches de convolution de manière décroissante et 2 couches pour la décision de braquage, avec le dropout pour désactiver les .
Parcontre pour le cas de GPU : on utilise les 5 couches de convolution et 4 couches pour la décision de braquage.

## Phase de test :

Durant le test :

1 - Le mode avec CPU peut effectuer 4 tours sans zigzager 
2 - Le mode en utilisant le GPU est limité à 0,5 tour et se met hors circuit.Réduire le degré de liberté : dropout ( mettre moins de couche et moins de neurone ) moins de chance de vous tromper .

## Interprétation du résultat 

### Mode cpu 
On voit qu'en utilisant un nombre restreint de reseau de neuronne, on peut avoir une excellente resultat car il traite les données essentielles de l'images pour choisir l'angle de braquage.
##### simulation
[![](http://img.youtube.com/vi/iBu57nVHUb8/0.jpg)](http://www.youtube.com/watch?v=iBu57nVHUb8 "self driving car using CPU")

### Mode GPU
Utiliser un grand nombre de réseau de neuronne , c'est de traiter une quantité de donnée importante.Donc on a besoin d'un puissance de puissance de calcul coûteuse, alors on  utiliser la puissance des GPU (unités de traitement graphiques).
##### Carte graphique
![alt text](https://github.com/Louis86/selfdrivingCar/blob/master/GPU.jpg)
##### Simulation 
[![](http://img.youtube.com/vi/O9PHgNqd-wY/0.jpg)](http://www.youtube.com/watch?v=O9PHgNqd-wY "self driving car using GPU")


Ici , On a un processeur graphique qui n'est pas NVIDIA donc qui n'est pas adequate à la puissance nécessaire pour éxecuter les couches de neuronnes en série donc ce qui explique le zigzag de la voiture

## Conclusion 
Faire un CNN avec le nombre de couche minimum est possible si on utilise des données images qui ne contient pas une grande nombre d'information . Par contre des qu'on veut généraliser un problème ou l'information sur une image contient beaucoup d'information nécessaire on doit établir plusieurs couche de neuronne en couche et c'est pour la nécéssité de traitement de donnée par la carte graphique .
