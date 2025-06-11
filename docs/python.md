# Python en Physique-Chimie
{{ initexo(0) }}



## Chapitre 1

!!! example "{{ exercice() }} : Corps pur ou mélange"
    === "Énoncé"
        1. Le programme suivant doit permettre de déterminer si l'on a affaire à un corps pur ou à un mélange. Ouvrir le script suivant dans Capytale (**code :**):
           ```python  linenums="1"
           # Corps pur ou mélange 
           observation = input("La température du corps est-elle constante lors du changement d'état ? ")
           if observation == "je réfléchis":
               print("Il s'agit d'un corps pur car la température de changement d'état d'un corps pur est constante.")
           else:
               print("Il s'agit d'un mélange car la température de changement d'état d'un mélange n'est pas constante.")
           ```
        2. À la ligne 3, remplacez la chaîne de caractère "je réfléchis" par oui (sans guillemets) ou par non (sans guillemets) ou par la chaîne de caractère "oui" ou par la chaîne de caractère "non" puis testez le programme pour vous assurer que vous avez fait le bon choix.
        3. Autres sources d'erreurs :
            1. Essayez de ne mettre qu'un seul `=` dans le test de comparaison à la ligne 3 puis testez le programme. Que constatez-vous ?
            2. Essayez de retirer le caractère `:`à  la fin de la ligne 3 ou à la fin de la ligne 5 et testez le programme. Que constatez-vous ?
            3. Essayez de retirer les indentations (c'est-à-dire le décalage) au début des lignes 4 et 6 et testez le programme. Que constatez-vous ?
                - **Données :**
                    - Python souhaite une information de l'utilisateur : `input()` retourne la saisie de l'utilisateur sous forme de chaîne de caractère. 
                    - Comme tous les langages de programmation, Python a des exigences de syntaxe. Il convient de les respecter.
               


## Chapitre 2
!!! example "{{ exercice() }} : Déterminer une concentration (chap02 ex 28 p 56)"
    === "Énoncé"
        1. Le programme suivant permet de déterminer la concentration en masse de chlorure de sodium d’une solution. Ouvrir le script suivant dans Capytale (**code :**):
           ```python  linenums="1"
           # Déterminer une concentration (chap02 ex 28 p 56)
           m = float(input("Masse de chlorure de sodium en g : "))
           V = float(input("Volume de la solution en L : "))
           t = m / V
           if t > 360:
               print("La concentration en masse t = 360 g/L")
           else:
               print("La concentration en masse :", t, "g/L")
           ```
        2. Donner le mode de préparation de la solution S
        3. La ligne 1 correspond à un commentaire. Par quel caractère doit-on commencer une ligne de commentaire ?
        4. Préciser l’objectif de `float()` aux lignes 2 et 3.
        5. Donner le nom de la fonction python utilisée aux lignes 6 et 8 qui permet d'afficher un message à l'écran.
        6. Modifier le programme afin de pouvoir déterminer la masse à prélever connaissant la concentration et le volume. 
              - **Données :**
                - À température ambiante, la concentration maximale en chlorure de sodium d’une solution est égale à 360 g·L<sup>–1</sup>.
                - Python et les nombres : python manipule soit des nombres entiers (`int`) comme 360 soit des nombres réels (`float`) comme 3,14.
                - Python souhaite une information de l'utilisateur : `input()` retourne la saisie de l'utilisateur sous forme de chaîne de caractère. 


## Chapitre 3
!!! example "{{ exercice() }} : Tracer les vecteurs vitesse avec pyplot (32 p 184)"
    === "Énoncé"
        1. Ouvrir le script suivant dans Capytale (**code :**):
           ```python  linenums="1"
           # Tracer les vecteurs vitesse (capytale c09e32p184)
           import matplotlib.pyplot as plt
           x=[0.0257,0.2877,0.5549,0.8118,1.0842,1.3256,1.6031]
           y=[1.0944,1.4387,1.5980,1.6133,1.4849,1.2177,0.7810]
           t=[0,0.125,0.25,0.375,0.5,0.625,0.75]
           # Calcul des composantes Vx et Vy
           Vx=[]
           for i in range(len(x)-1) :
               Vxi=[(x[i+1]-x[i])/(t[i+1]-t[i])]
               Vx= Vx+ Vxi
           Vy=[]
           for i in range(len(y)-1) :
               Vyi=[(y[i+1]-y[i])/(t[i+1]-t[i])]
               Vy=Vy+Vyi
           # préparation de la zone graphique
           plt.grid()
           plt.title("Représentation du vecteur vitesse")
           plt.xlabel('$x$ (m)')
           plt.ylabel('$y$ (m)')
           # tracé des points de la trajectoire
           plt.plot(x,y,'ro')
           # tracé des vecteurs vitesse avec un facteur d'échelle
           for i in range(len(t)-1):
               plt.arrow(x[i],y[i],Vx[i]/10, Vy[i]/10,head_width=0.03, head_length=0.03,color="blue")
               plt.text(x[i]+0.05,y[i],r"$\vec{v}$"+str(i+1),color="blue")
           # Légende
           plt.text(0.1,0.8,"Echelle 1 cm $\leftrightarrow$ 10 cm/s", color="blue")
           plt.show()
           ```
           2. Repérer dans le programme les lignes correspondant aux données extraites du pointage.
           3. Repérer de même la (ou les) ligne(s) permettant de représenter les vecteurs vitesse. Extraire de cette (ou ces) ligne(s) le facteur de représentation des vecteurs vitesse.
           5. Proposer une modification du programme pour avoir un facteur de représentation des vecteurs vitesse de 1/15.


## Chapitre 4

## Chapitre 5


```python  linenums="1"
t  = [0, 0.04, 0.08, 0.12, 0.16, 0.20, 0.24]
# d  = 0 0.008 0.031 0.071 0.125
d = [4.9* dt**2 for dt in t]
# v (m/s)0.20 0.58 0.98 1.40
v = [d[i]/t[i] for i in len(t)]
```



## Chapitre 6






## Chapitre 7
!!! example "{{ exercice() }} : Obtenir une configuration électronique (chap04 ex 33 p 95)"
    === "Énoncé"
        1. Ouvrir le script suivant dans Capytale (**code :**):
           ```python  linenums="1"
           # Obtenir une configuration électronique (capytale c04e33p95)
           Z = int(input("Que vaut Z (Z < 18) ?"))
           ne = Z # (1)
           # initialisation: les sous-couches électroniques sont vides
           n1s = 0
           n2s, n2p = 0, 0
           n3s, n3p = 0, 0

           # Remplir sous-couche 1s
           while (ne > 0) and (n1s < 2): # (4)
               n1s += 1 # (2)
               ne -= 1  # (3)
               if (ne == 0) or (n1s == 2):
                   config = " 1s" + str(n1s) # (5)

           # Remplir sous-couche 2s
           while (ne > 0) and (n2s < 2):
               n2s += 1
               ne -= 1
               if (ne == 0) or (n2s == 2):
                   config = config + " 2s" + str(n2s) # (6)

           # Remplir sous-couche 2p
           while (ne > 0) and (n2p < 6):
               n2p += 1
               ne -= 1
               if (ne == 0) or (n2p == 6):
                   config = config + " 2p" + str(n2p) # (7)

           # Remplir sous-couche 3s
           while (ne > 0) and (n3s < 2):
               n3s += 1
               ne -= 1
               if (ne == 0) or (n3s == 2):
                   config = config + " 3s" + str(n3s) # (8)

           # Remplir sous-couche 3p
           
           
           
           
           
           
           if ne > 0:
               print("hors programme")
           else:
               print("Pour Z =", Z, "la configuration électronique est", config)
        
           ```
            1. Nombre d'électrons à placer sur les différentes sous-couches
            2. Incrémente le nombre d'électrons sur la sous-couche 1s
            3. Décrémente le nombre total d'électrons restant à placer
            4. Tant qu'il reste des électrons à placer et que la sous-couche 1s n'est pas pleine, continuer de remplir la sous-couche 1s
            5. Commence une chaîne de caractères qui va débuter par *1s* suivi du nombre d'électrons sur cette sous couche. La fonction `str()` transforme un entier en chaine de caractère
            6. Prolonge la chaîne nommée`config`
            7. Prolonge la chaîne nommée`config`
            8. Prolonge la chaîne nommée`config`
        2. En utilisant le script déterminer la configuration électronique de l'hélium $He$(Z = 2) et du berrylium $Be$(Z = 4).
        3. Compléter le script pour la sous-couche 3p 
        4. En utilisant le script déterminer la configuration électronique de l'alluminium $A\ell$(Z = 13).
    === "Correction"
        ```python  linenums="1"
        # Obtenir une configuration électronique (capytale c04e33p95)
        Z = int(input("Que vaut Z (Z < 18) ?"))
        ne = Z # (1)
        # initialisation: les sous-couches électroniques sont vides
        n1s = 0
        n2s, n2p = 0, 0
        n3s, n3p = 0, 0

        # Remplir sous-couche 1s
        while (ne > 0) and (n1s < 2): # (4)
            n1s += 1 # (2)
            ne -= 1  # (3)
            if (ne == 0) or (n1s == 2):
                config = " 1s" + str(n1s) # (5)

        # Remplir sous-couche 2s
        while (ne > 0) and (n2s < 2):
            n2s += 1
            ne -= 1
            if (ne == 0) or (n2s == 2):
                config = config + " 2s" + str(n2s)

        # Remplir sous-couche 2p
        while (ne > 0) and (n2p < 6):
            n2p += 1
            ne -= 1
            if (ne == 0) or (n2p == 6):
                config = config + " 2p" + str(n2p)

        # Remplir sous-couche 3s
        while (ne > 0) and (n3s < 2):
            n3s += 1
            ne -= 1
            if (ne == 0) or (n3s == 2):
                config = config + " 3s" + str(n3s)

        # Remplir sous-couche 3p
        while (ne > 0) and (n3p < 6):
            n3p += 1
            ne -= 1
            if (ne == 0) or (n3p == 6):
                config = config + " 3p" + str(n3p)
        
        if ne > 0:
            print("hors programme")
        else:
            print("Pour Z =", Z, "la configuration électronique est", config)
     
        ```
     

## Chapitre 8
!!! example "{{ exercice() }} : Fonction périodique (chap12 ex 23 p 241)"
    === "Énoncé"
        1. Ouvrir le script suivant dans Capytale (**code :**):
           ```python  linenums="1"
           import matplotlib.pyplot as plt
           import numpy as np
           
           
           # Création d'une variable temps, t, dont 1000 valeurs sont comprises entre 0 et 0,1 seconde
           t = np.linspace(0, 0.1, 1000)

           # valeur ....
           f = 100
           f1 = 100
           
           # Définition des fonctions y et y1 (et y2 à compléter)
           y = 3 * np.sin(2 * np.pi * f * t)
           y1 = 3 * np.sin(2 * np.pi * f1 * t) + 3 * np.sin(4 * np.pi * f1 * t)
           
           # Tracé des courbes sous forme de graphiques empilés dans une grille et mise en place de la légende
           plt.gcf().subplots_adjust(hspace=0.8) # (1)
           plt.title("Acquisition de deux signaux sonores")
           
           # Tracé de y
           plt.subplot(2, 1, 1) # (2)
           plt.xlabel('$t$ (en s)')
           plt.ylabel('$y$')
           plt.grid()
           plt.plot(t, y, color='blue')
           
           # Tracé de y1
           plt.subplot(2, 1, 2) # (3)
           plt.plot(t, y1, color='red')
           plt.xlabel('$t$ (en s)')
           plt.ylabel('$y_1$')
           plt.grid()
           
           # Tracé de y2 (à compléter)
           
           # (4) 
           
           # Affichage de la figure 
           plt.show()
           ```
            1. height space (espace en hauteur) entre lignes de la grille. Au besoin, utiliser `wspace` comme width space pour régler l'espace en largeur entre colonnes.
            2. Dans une grille de 2 lignes x  1 colonne, la figure est placée en  1re ligne. À modifier à la question 6.
            3. Dans une grille de 2 lignes x  1 colonne, la figure est placée en  2e ligne.  À modifier à la question 6.
            4. On peut également sauvegarder l'image dans le répertoire du script avec `plt.savefig("image.png")` 
        2. Déterminer graphiquement la période de chacune des fonctions correspondant aux courbes
        3. Calculer la fréquence de chacune de ces deux fonctions.
        4. Compléter le commentaire de la ligne 8 du programme.
        5. À l’aide de la représentation temporelle de la fonction `y`, indiquer ce que représente le nombre 3 dans la ligne 13 du programme.
        6. Sous le tracé des deux fonctions précédentes, on souhaite tracer une nouvelle fonction `y2` qui est sinusoïdale, de période T égale à 0,020 s et d’amplitude égale à 4. Modifier le programme  (`f2 = ?` ; `y2 = ?` ; Tracé de y2) pour afficher le tracé des trois fonctions. Utiliser `plt.subplot(3, 1, 1)`, `plt.subplot(3, 1, 2)` et `plt.subplot(3, 1, 3)` pour placer les sous figures dans une grille 3x1.
    



## Chapitre 12

!!! example "{{ exercice() }} : Lentille"
    === "Énoncé"
        1. Ouvrir et tester le script suivant dans Capytale (**code :**):    
           ```python  linenums="1"
           # Fonction permettant de calculer la taille de l'image
           def calculer_taille_image(AB, OA, OAprime):
               AprimeBprime = AB * OAprime / OA
               return AprimeBprime


           # Les valeurs sont fournies par l'utilisateur
           AB = float(input("Donner la taille de l'objet AB en mètre : \n"))
           OA = float(input("Donner la distance OA en mètre : \n"))
           OAprime = float(input("Donner la distance OA' en mètre : \n"))
           
           # Calcul et affichage du résultat
           resultat = calculer_taille_image(AB, OA, OAprime)
           print("La taille de l'image A'B' est", resultat, "m.")
           ```
           2. Écrire un nouveau programme comportant la fonction `calculer_position_image(AB, OA, AprimeBprime)` qui permet de calculer OA’ connaissant AB, OA et A'B' qui seront les valeurs fournies par l'utilisateur. 
           3. Adapter la partie *Calcul et affichage du résultat* pour afficher la position de l'image.



## Chapitre 14

!!! example "{{ exercice() }} : Parafoudre (chap16 ex 28 p320)"
    === "Énoncé"
        -  Réaliser l'exercice dans Capytale
