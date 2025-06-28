# Chapitre IV : Modéliser une action mécanique

{{ initexo(0) }}


## Exemple de situation

Alice (à gauche de l'image) s'apprête à smasher le ballon de volley envoyé par Béatrice. On veut représenter les forces qui s'exercent sur le ballon au moment où la photo a été prise.

![image](data/chap4_voley.jpg){: .center .img-rounded width="300"}


## 1. Le système étudié
- Le système est l'objet étudié (ou un ensemble d'objets considérés comme un tout).
- Le système étudié est modélisé par un point matériel.
- Le **système** étudié peut être soumis à différentes actions mécaniques de la part de l'**extérieur** (tout ce qui ne fait pas partie du système étudié).

Pour l'exemple : L'objet constituant le système étudié est le `{ballon}`. Tout le reste (`Alice`, `Béatrice`, le `filet et ses poteaux`, l'`air`, la `Terre`...) constitue l'environnement extérieur.

Remarque : On ne considère ici que les objets matériels. La force exercée par Béatrice lors du lancer n'est pas un objet. De même, la vitesse du vent ou celle du ballon ne sont pas des objets. Cependant, préciser l'état des objets peut aider à identifier toutes les interactions. Par exemple, `ballon en mouvement` ou, en présence de vent, `air en mouvement`.


## 2. Diagramme objets-interactions

Le DOI (Diagramme Objets-Interactions) est un outil simple mais puissant qui permet de visualiser les interactions entre objets. Il facilite l'analyse des forces en ne conservant que celles qui s'appliquent au système étudié (ce qui permet d'éviter la confusion entre action et réaction).

Un diagramme objets-interactions permet de recenser toutes les interactions impliquant le système à un instant t. Les interactions à **distance** (sans contact entre les objets) sont représentées par des **pointillés**, tandis que les interactions de **contact** sont représentées par des **traits pleins**.


![image](data/chap4_DOI1.jpg){: .center width="400"}



## 3. Modélisation d'une action

- Chaque action est modélisée par une force. 
- Une force est représentée par un vecteur. 

Exemple: l'action mécanique exercée par la Terre sur le ballon est modélisée par une force $\vec F_{Terre/ballon} = \vec P$ (dont la valeur s'exprime en Newtons) qu'on appelle le poids (à ne pas confondre avec la masse qui s'exprime en kilogrammes).

!!! note "Le vecteur force $\vec F$"
    Comme tout vecteur, le vecteur force a :  
    • **une direction** : celle de la droite d'action de la force ;  
    • **un sens** : celui de la force ;  
    • **une norme** : $\left|\left| \vec F \right|\right|$ proportionnelle à $F$, la valeur de la force qui est en Newtons (N).  

!!! note "Point d'application d'une force"
    • Point où l'on considère que s'exerce la force.   
    • Quand le système est modélisé par un point, ce point est considéré comme point d'application de la force.


- Pour l'exemple étudié, on peut représenter deux forces :
    - Le poids $\vec P$ du ballon qui représente l'action de l'objet Terre sur le système {ballon}.
    - La force de frottements $\vec f$ qui représente l'action de l'air sur le ballon. 

!!! abstract "Caractéristique du vecteur $\vec P$"
    - **direction** : verticale  
    - **sens** : vers la Terre donc vers le bas  
    - **norme** : donnée par la formule $P = m \times g$   

!!! abstract "Caractéristique du vecteur $\vec f$"
    - **de direction** : tangente au mouvement  
    - **de sens** : vers la droite car inverse au sens du mouvement du ballon  
    - **de norme** : f de valeur inconnue  

![image](data/chap4_forces.jpg){: .center .img-rounded width="300"}
