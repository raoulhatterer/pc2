# Python en Physique-Chimie
{{ initexo(0) }}



## Chapitre 2
!!! example "{{ exercice() }} : Déterminer une concentration (28 p 56)"




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
!!! example "{{ exercice() }} : Fonction périodique (chap 12 ex 23 p 241)"
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
            2. Dans une grille de 2 lignes x  1 colonne, la figure est placée en  1re ligne
            3. Dans une grille de 2 lignes x  1 colonne, la figure est placée en  2e ligne
            4. On peut également sauvegarder l'image dans le répertoire du script avec `plt.savefig("image.png")` 
        2. Déterminer graphiquement la période de chacune des fonctions correspondant aux courbes
        3. Calculer la fréquence de chacune de ces deux fonctions.
        4. Compléter le commentaire de la ligne 8 du programme.
        5. À l’aide de la représentation temporelle de la fonction `y`, indiquer ce que représente le nombre 3 dans la ligne 13 du programme.
        6. Sous le tracé des deux fonctions précédentes, on souhaite tracer une nouvelle fonction `y2` qui est sinusoïdale, de période T égale à 0,020 s et d’amplitude égale à 4. Modifier le programme  (`f2 = ?` ; `y2 = ?` ; Tracé de y2) pour afficher le tracé des trois fonctions. Utiliser `plt.subplot(3, 1, 1)`, `plt.subplot(3, 1, 2)` et `plt.subplot(3, 1, 3)` pour placer les sous figures dans une grille 3x1.
    



## Chapitre 9
!!! example "{{ exercice() }} : Fonction périodique (23 p 241)"



!!! example "{{ exercice() }} : Bilan de matière"
    === "Énoncé"
        1. Compléter le code suivant dans Capytale (**Code :** 2787-6384519)
           ```python  linenums="1"
           ## Bilan de matière
           print("Équation de la réaction : aA + bB -> cC + dD")
           print("Entrez les valeurs des nombres stochiométriques:")
           a = float(input("a = ")) # (1)
           b = ... # à vous
           c = ... # à vous
           d = ... # à vous
           print("Entrez les quantités initiales de réactifs A et B en mol")
           nA = float(input("n0(A) = "))
           nB = float(input("n0(B) = "))
           # Détermination de xmax et du réactif limitant
           xmaxA, xmaxB = nA / a, nB / b # (2)
           if xmaxA == xmaxB: # (3)
               print("Le mélange est stoichiométrique")
               xmax = xmaxA
           elif xmaxA < xmaxB:
               print("...  est le réactif limitant") # à vous
               xmax = xmaxA # (4) 
           else:
               print("...  est le réactif limitant") # à vous
               xmax = xmaxB # (5)
           print(f"xmax = {xmax} mol")
           # Détemination des quantités de matière à l'état final        
           nfA, nfB = nA - a * xmax, nB - b * xmax # (6) 
           nfC, nfD = c * xmax, d * xmax # (7)
           print("Quantités de matière à l'état final")
           print(f"nf(A) = {nfA} mol")
           print(f"nf(B) = {nfB} mol")
           print(f"nf(C) = {nfC} mol")
           print(f"nf(D) = {nfD} mol")
           ```
            1. La fonction `input()` renvoie le texte (on parle de chaîne de caractère) saisie par l'utilisateur (par exemple la chaîne `"1"`) . Ensuite la chaîne peut être convertie en entier avec la fonction `int()` (soit pour l'exemple, l'entier `1`) ou en réel avec la fonction `float()` comme c'est le cas ici (soit pour l'exemple, le flottant `1.0`).
            2. Réalisation d'une double affectation en une seule ligne. À la place, on aurait pu écrire `xmaxA = nA / a` sur une ligne et sur la ligne suivante on aurait écrit `xmaxB = nB / b`.
            3. En python le symbole d'égalité n'est pas `=` mais `==` car en python le signe égal est utilisé pour les affectations. Une affectation ressemble parfois à une égalité ; par exemple si l'on écrit `x = 5`. Mais, ce n'en est pas une, comme on le voit quand on écrit `x = x+1` qui n'a pas le sens mathématique d'égalité, mais le sens informatique d'affectation conduisant ici à `x = 6`. 
            4. Ceci n'est pas une égalité, c'est une affectation.
            5. Ceci n'est pas une égalité, c'est une affectation.
            6. Double affectation pour les réactifs restants.
            7. Double affectation pour les produits formés.

        2. Utiliser le programme précédent pour résoudre l'exercice suivant:
           ![ex9p59](data/ex9p59.png){ width="50%" }

    === "Correction"
        1. Code source (ex 23 page 63):
        ``` python  linenums="1"
        ## Bilan de matière
        print("Équation de la réaction : aA + bB -> cC + dD")
        print("Entrez les valeurs des nombres stochiométriques:")
        a = float(input("a = "))
        b = float(input("b = "))
        c = float(input("c = "))
        d = float(input("d = "))
        print("Entrez les quantités initiales de réactifs A et B en mol")
        nA = float(input("n0(A) = "))
        nB = float(input("n0(B) = "))
        # Détermination de xmax et du réactif limitant
        xmaxA, xmaxB = nA / a, nB / b
        if xmaxA == xmaxB:
            print("Le mélange est stoichiométrique")
            xmax = xmaxA
        elif xmaxA < xmaxB:
            print("A est le réactif limitant")
            xmax = xmaxA
        else:
            print("B est le réactif limitant")
            xmax = xmaxB
        print(f"xmax = {xmax} mol")
        # Détemination des quantités de matière à l'état final
        nfA, nfB = nA - a * xmax, nB - b * xmax
        nfC, nfD = c * xmax, d * xmax
        print("Quantités de matière à l'état final")
        print(f"nf(A) = {nfA} mol")
        print(f"nf(B) = {nfB} mol")
        print(f"nf(C) = {nfC} mol")
        print(f"nf(D) = {nfD} mol")
        ```        
        **Remarque :** On peut comparer le code précédent à celui donné à l'exercice 23 page 63 qui semble un peu plus compliqué car il utilise `"\n"` pour des retours à la ligne et `.format()` plutôt que d'utiliser des `fstring`.
        2. Exécuter le programme et saisir  `a = 1`, `b = 2`, `c = 1` et `d = 0` puis `n0(A) = 5` et `n0(B) = 5`.
        ```pycon
        Équation de la réaction : aA + bB -> cC + dD
        Entrez les valeurs des nombres stochiométriques:
        a = 1
        b = 2
        c = 1
        d = 0
        Entrez les quantités initiales de réactifs A et B en
         mol
        n0(A) = 5
        n0(B) = 5
        B est le réactif limitant
        xmax = 2.5 mol
        Quantités de matière à l'état final
        nf(A) = 2.5 mol
        nf(B) = 0.0 mol
        nf(C) = 2.5 mol
        nf(D) = 0.0 mol
        ```


    
!!! example "{{ exercice() }} : Titrage"
    === "Énoncé"
        1. Compléter le code suivant dans Capytale (**Code :** df61-6385666)
           ```python  linenums="1"
           ## Titrage
           print("Titrage de  A par B : aA + bB -> cC +dD")
           print("Entrez les valeurs des nombres stœchiométriques a et b")
           a = float(input("a = "))
           b = float(input("b = "))
           print("Entrez des volumes en mL et la concentration CB en mol/L")
           VA = ... # à vous
           VE = ... # à vous
           CB = ... # à vous
           # Calcul de CA
           CA = ... # à vous
           print(f"Concentration CA = {CA} mol/L")
           ```
           
        2. Utiliser le programme précédent pour résoudre l'exercice suivant:
           ![ex6p74](data/ex6p74.png){ width="50%" }

    === "Correction"
        1. Code source (ex 13 page 75):
        ``` python  linenums="1"
        ## Titrage
        print("Titrage de  A par B : aA + bB -> cC +dD")
        print("Entrez les valeurs des nombres stœchiométriques a et b")
        a = float(input("a = "))
        b = float(input("b = "))
        print("Entrez des volumes en mL et la concentration CB en mol/L")
        VA = float(input("VA = "))
        VE = float(input("VE = "))
        CB = float(input("CB = "))
        CA = (a/b)*(CB*VE/VA)
        print(f"Concentration CA = {CA} mol/L")
        ```
        2. Exemple
        ```pycon
        Titrage de  A par B : aA + bB -> cC + dD
        Entrez les valeurs des nombres stœchiométriques a et b
        a = 1
        b = 3
        Entrez des volumes en mL et la concentration CB en mol/L
        VA = 10
        VE = 13.8
        CB = 0.0025
        Concentration CA = 0.00115 mol/L
        ```


           

!!! example "{{ exercice() }} : Bilan de puissance et Rendement électrique"
    === "Énoncé"
        1. Pour réaliser le bilan de puissance d'une source de tension continue, un élève écrit une fonction  en langage Python. D'après le programme, par quel type de source de tension, la source est-elle modélisée ?
           ```python  linenums="1"
           ## Bilan de puissance et rendement
           def BILAN_PUISSANCES(E,r,I) :
               U = E-r*I
               Pj = r*I**2
               Pa = E*I
               Pu = U*I
               print("La puissance chimique absorbée en entrée vaut Pa =",Pa,"W. \n")
               print("La puissance dissipée par effet Joule vaut Pjoule = ",Pj,"W. \n")
               print("La puissance électrique utile en sortie vaut Pu = ",Pu,"W. \n")
               rendement = ... à vous
               print ... à vous
           ``` 
        2. Identifier les lignes de programme qui permettent de calculer les puissances nécessaires au calcul du rendement de la source de tension.
        3. Compléter ce programme pour que la fonction calcule et affiche le rendement de la source de tension. Compléter le code  dans Capytale (**Code :** 6e56-6486645)
        4. Utiliser le programme précédent pour résoudre l'exercice 19 page 250:
           ![ex19p250](data/p250.png){ width="50%" }
        
    === "Correction"{#
        1. Code source (ex 18 page 250):
        ``` python  linenums="1"
        ## Bilan de puissance et rendement
        def BILAN_PUISSANCES(E,r,I) :
            U = E-r*I
            Pj = r*I**2
            Pa = E*I
            Pu = U*I
            print("La puissance chimique absorbée en entrée vaut Pa =",Pa,"W. \n")
            print("La puissance dissipée par effet Joule vaut Pjoule = ",Pj,"W. \n")
            print("La puissance électrique utile en sortie vaut Pu = ",Pu,"W. \n")
            rendement = Pu/Pa
            print("Le rendement vaut: ",rendement,".\n")
        ```  #}


!!! example "{{ exercice() }} : Simulation de la propagation d'une onde"
    === "Énoncé"
        Exercice 28 page 299 (Capytale c621-6680926)
