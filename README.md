## IA LAB : SELF DRIVING CAR

# Introduction 
Actuellement, il y a un nombre croissante sur l'utilisation de l' IA. l'intélligence artificielle ?  permet de doter à un ordinateur la capacité de faire des tâches comparable à un être humain.


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
C’est un technique d'apprentissage supervisé. On reçoit les images en entrée et on prédit l’angle de braquage. 
 Le premier réseau de neurone applique les opérations de filtrage avec plusieurs noyaux de convolutions, puis redimensionne . L'objectif est de traiter les images et d’extraire les informations importantes. On applique le technique de Pooling, qui signifie de ne garder que les données nécessaires . On utilise aussi le dropout , qui permet de désactiver certain neurone. Puis, on fa utiliser flatten permettant de créer le vecteur final au réseau de neurone. Le second réseau de neuron permet de prédire l’angle de braquage en fonction des information issus des réseaux de neurones précédentes.

# # Raison pour l'utilisation de CNN : 
On cherche à améliorer la matrice de convolution avec les données images ont a une grande donnés à cause de l’énorme quantité de donnée donc il faut le réduire par pooling .

80 % donnée d'entraînement 
20 % de donnée pour le test


A partir de l’exemple vers le vrais monde
Réduire le degré de liberté : dropout ( mettre moins de couche et moins de neurone ) moins de chance de vous tromper .

A l’inverse un petit réseau et un petit donné  ( faire une chose qui ne se généralise pas au monde )

Réseau de neurone beaucoup de donnée

Plus de neurone 

Architecture de réseau n’est pas adapté 

Jolie image 2D et on a aplati  On a perdu .

2D réseau conventionnelle 

somme pondérée de pixelles 
1 neuronne  somme ponderée de pixelles autours de luis 4*4 au lieu de faire une somme ponderé de toute l’image 4 * 4

2 différence , même poids que sont voisin entre 2 neuronnes  4* 4 * 3  W  ( 48 poids ) 

plus de degré de liberté avec une autre matrice de poids 


d autre neuronne qui dit j ai rien vu et d autre qui di j ai vu ce que je suis spécialisé pour voir

chaque neuronne a sa propre poids 

2conv2d double boucle sur l image 

arriver à 99 restreindre à tout petit peux de dégré de liberté ( nombre de calcul necessaire ) 

Nombre de precision ( dropout) 


nombre  patch à ajouter pas mal de liberté en plus 

