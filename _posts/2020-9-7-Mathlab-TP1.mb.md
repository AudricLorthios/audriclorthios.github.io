---
layout: post
title: Matlab TP1
---

## 1) Premier contact



## 2) Premières instructions

### 1. Ecrivez l'instruction 5+8

#### a) Que se passe-il dans la fenêtre de commande ?

```matlab
>> 5+8

ans =

    13
```

#### b) Que se passe-t-il dans le Workspace ?

La variable `ans` à été crée et elle a pris la valeur de 13



### 2. Ecrivez l'instruction x = pi/4

#### a) Que se passe-il dans la fenêtre de commande ?

```matlab
>> x= pi/4

x =

    0.7854
```

#### b) Que se passe-t-il dans le Workspace ?

la variable `x` a été crée et elle a pris la valeur de 0.7854



### 3. Ecrivez l'instruction x = pi/6;

#### a) Que se passe-il dans la fenêtre de commande ?

```matlab
>> x= pi/6

x =

    0.5236
```

#### b) Que se passe-t-il dans le Workspace ?

La valeur de la variable `x` à été changée.



### 4. Quelles instructions vous permettent d'affecter aux variables y1 et y2 les valeurs de sin(x) et cos(x) ?

Vous ferez en sorte que le résultat ne s'affiche pas dans la fenêtre de commande.

```matlab
>> y1 = sin(x); y2 = cos(x);
```

> Note: quand on met ; a la fin de instruction, le résultat ne s'affiche pas



### 5. En utilisant les variables crées, quelle instruction vous permet de vérifier que cos² (x) + sin² (x) = 1 ?

Cette fois, le résultat devra apparaitre dans la fenêtre de commande.

```matlab
>> y1^2+y2^2

ans =

     1
```



## 3) Vecteurs et matrices

### 3.1 Construction explicite

| Types :             | Déclaration :         | Description                                                  |
| ------------------- | --------------------- | ------------------------------------------------------------ |
| **Vecteur ligne**   | [1 2 3] ou [1, 2, 3]  | Les crochets marquent le début et la fin du vecteur, et les espaces ou les virgules délimitent ses différents coefficients |
| **Vecteur colonne** | [1; 2; 3]             | Le point virgule permet de séparer les différents coefficients, et correspond donc en pratique à un retour à la ligne. |
| **Matrice**         | [1 2 3; 4 5 6; 7 8 9] | Les coefficients sont donc entrés ligne par ligne, chacune de ces dernières étant finie par un point virgule |



#### 1. Quelle instruction permet de créer une variable x sous la forme d'un vecteur ligne contenant π/6, π/4, π/3?

```matlab
>> x = [pi/6 pi/4 pi/3]

x =

    0.5236    0.7854    1.0472
```

> Note: ici je n'ai pas mis de "," car il n'est pas nécessaire



#### 2.  Quelle instruction permet de créer une matrice M de dimension 3X3 de sorte que la première ligne contienne x, tandis que les deuxième et troisième ligne contiennent respectivement cos(x) et sin(x) ?

##### a) Une premières fois en remplissant explicitement chaque case

```matlab
>> M = [pi/6 cos(pi/6) sin(pi/6); pi/4 cos(pi/4) sin(pi/4); pi/3 cos(pi/3) sin(pi/3)]

M =

    0.5236    0.8660    0.5000
    0.7854    0.7071    0.7071
    1.0472    0.5000    0.8660
```



##### b) une seconde fois en réfléchissant un peu plus ! 

```matlab
>> M = [x; cos(x); sin(x)]

M =

    0.5236    0.7854    1.0472
    0.8660    0.7071    0.5000
    0.5000    0.7071    0.8660
```

> Note: ici j'ai mis des ";" car je veut écrire les valeurs en colonnes



### 3.2 Construction rapide

#### Vecteur

| Déclaration         | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| **n:m**             | Création du vecteur contenant les nombres de **n** à **m** par pas de **1** |
| **n:p:m**           | Création du vecteur contenant les nombres de **n** à **m** par pas de **p** |
| **linspace(n,m,p)** | Création du vecteur contenant **p** nombres de **n** à **m** |
| **[x,y]**           | Création du vecteur en contenant la concaténation des vecteurs **x** et **y** |
| **reshape(x,u,v)**  | Crée une matrice de taille **[u,v]** à partir de **x**       |



#### Matrice Particulière

| Déclaration    | Description                                                  |
| -------------- | ------------------------------------------------------------ |
| **zeros(m,n)** | Crée une matrice nulle de taille **m**,**n**                 |
| **ones(m,n)**  | Crée une matrice de taille **m**,**n** dont tous les coefficients valent **1** |
| **eye(n)**     | Crée la matrice identité de taille **n**                     |
| **diag(x)**    | Crée une matrice diagonale dont la diagonale est le vecteur **x** |
| **magic(n)**   | Crée un carré magique de taille **n**                        |
| **rand(m,n)**  | Crée une matrice de taille **m**,**n**, à coefficients aléatoires uniformément sur [0,1] |
| **randn(m,n)** | Crée une matrice de taille **m**,**n**, à coefficients aléatoires de la loi normale N(0,1) |



#### 1. Quelle instruction permet de crée un vecteur contenant les valeurs de -8 à -5 avec un pas de 0.25

```matlab
>> V = -8:0.25:-5

V =

   -8.0000   -7.7500   -7.5000   -7.2500   -7.0000   -6.7500   -6.5000   -6.2500   -6.0000   -5.7500   -5.5000   -5.2500   -5.0000
```



#### 2. Quelle instruction permet de créer un vecteur de longueur 100 de −π à π ?

```matlab
>> linspace(-pi,pi,100)
```

> Note: Je n'ai pas mis le résultat car il est trop grand



#### 3. Quelle instruction permet de créer une matrice de dimension 10X10 contenant tous les nombres entiers de 1 à 100 dans l'ordre croissant (la première colonne contiendra les nombres de 1 à 10)?  

```matlab

```

> Note: je suis pas sur de moi donc il faudra que je demande au prof

#### 4. Quelle instruction permet de créer une matrice diagonale dont les valeurs non nulles sont toutes des nombres aléatoires (loi uniforme) de l'intervalle [0, 5].

```matlab

```

> Note: je suis pas sur de moi donc il faudra que je demande au prof



### 3.3 Extraction de composantes

| Argument            | Définition                                           |
| ------------------- | ---------------------------------------------------- |
| **size(A)**         | obtenir le nombre de lignes et de colonnes de **A**  |
| **A(i,j)**          | obtenir le coefficient d'ordre **i**, **j** de **A** |
| **A(i1:i2,:)**      | obtenir les lignes de **i1** à **i2** de **A**       |
| **A(i1:i2,:) = []** | supprimer les lignes **i1** à **i2** de **A**        |
| **A(:,j1:j2)**      | obtenir les colonnes de **j1** à **j2** de **A**     |
| **A(:,j1:j2) = []** | supprimer les colonnes**j1** à **j2** de **A**       |
| **A(:)**            | indexation linéaire de **A**                         |
| **A(i)**            | coefficient d'ordre **i** indexation linéaire        |
| **diag(A)**         | obtenir les coefficients diagonaux de **A**          |



#### 1) Créez une matrice A de 3 × 3 contenant dans l'ordre croissant les nombres entiers de 1 à 9.

```matlab
>> 1:9

ans =

     1     2     3     4     5     6     7     8     9

>> A = [ans(1:3);ans(4:6);ans(7:9)]

A =

     1     2     3
     4     5     6
     7     8     9
```



##### a) Quelle instruction permet de récupérer la deuxième colonne ?

```matlab
>> A(:,2)

ans =

     2
     5
     8
```



##### b) Quelle instruction permet de récupérer les deux dernières lignes ?

```matlab
>> A(:,2:3)

ans =

     2     3
     5     6
     8     9
```

> Note: ici nous affichons que les 2 dernières lignes

ou

```matlab
>> A(:,1)=[]

A =

     2     3
     5     6
     8     9
```

> Note: ici nous supprimons la premières colonnes



##### c) Quelle instruction permet de générer une matrice 2 × 2 contenant seulement les 4 coins ?

```matlab
>> A(1:2:3,1:2:3)

ans =

     1     3
     7     9
```



##### d) Quelle instruction permet de générer un vecteur contenant les nombres entiers de 1 à 9 dans l'ordre croissant ?

```matlab
>> 1:9

ans =

     1     2     3     4     5     6     7     8     9
```



#### 2) Créez deux vecteurs x = [1 2 3 4 5 6] et y = [7 8 9 10 11 12] (avec élégance bien sur)

```matlab
>> x = [1:1:6]

x =

     1     2     3     4     5     6

>> y = [7:1:12]

y =

     7     8     9    10    11    12

```



##### a) Quelle instruction permet de générer la matrice M1 = 

$$
M1=
\left(\begin{array}{cc} 
1 & 2 & 3\\
7 & 8 & 9
\end{array}\right)
$$

```matlab
>> M1=[x(1:3);y(1:3)]

M1 =

     1     2     3
     7     8     9
```



##### b) Quelle instruction permet de générer la matrice M2

$$
M2=
\left(\begin{array}{cc} 
1 & 2 & 3&7&8&9\\
4 & 5 & 6&10&11&12
\end{array}\right)
$$

```matlab
>> M2=[x(1:3) y(1:3) ; x(4:6) y(4:6)]

M2 =

     1     2     3     7     8     9
     4     5     6    10    11    12
```



##### c) Quelle instruction permet de générer la matrice M3

$$
M3=
\left(\begin{array}{cc} 
1&2&3\\
8&10&12
\end{array}\right)
$$

```matlab
>> M3=[x(1:2:5);y(2:2:6)]

M3 =

     1     3     5
     8    10    12
```



#### 3) En utilisant les matrices qui viennent d'être créées, quelle instruction permet de générer la matrice suivante :

$$
M=
\left(\begin{array}{cc} 
0&0&0&1&2&3\\
0&0&0&7&8&9\\
1&2&3&7&8&9\\
4&5&6&10&11&12\\
1&2&3&4&5&6\\
7&8&9&10&11&12
\end{array}\right)
$$

```matlab
>> Z = zeros(2,3)

Z =

     0     0     0
     0     0     0
     
>> M = [Z M1; M2 ; X;Y]

M =

     0     0     0     1     2     3
     0     0     0     7     8     9
     1     2     3     7     8     9
     4     5     6    10    11    12
     1     2     3     4     5     6
     7     8     9    10    11    12
```



### 3.4  Opérations matricielles

| Argument         | Définition                                   |
| ---------------- | -------------------------------------------- |
| **A'**           | Transposée de **A**                          |
| **rank(A)**      | rand de **A**                                |
| **inv(A)**       | inverse de **A**                             |
| **expm(A)**      | exponentielle de **A**                       |
| **det(A)**       | déterminant de **A**                         |
| **trace(A)**     | trace de **A**                               |
| **poly(A)**      | polynôme caractéristique de **A**            |
| **eig(A)**       | valeurs propres de **A**                     |
| **[U,D]=eig(A)** | vecteurs propres et valeurs propres de **A** |
| **+** et **-**   | addition, soustraction                       |
| ***** et **^**   | multiplication, puissance (matricielles)     |
| **.*** et **.^** | multiplication, puissance **terme à terme**  |
| **A\b**          | Solution de **Ax = b**                       |
| **b/A**          | Solution de **xA=b**                         |
| **./**           | Division **terme à terme**                   |



#### 1) En reprenant la matrice M de l'exercice précédent :

```matlab
>> M

M =

     0     0     0     1     2     3
     0     0     0     7     8     9
     1     2     3     7     8     9
     4     5     6    10    11    12
     1     2     3     4     5     6
     7     8     9    10    11    12
```



#####  a) Créez la matrice Mt égale à la transposée de M ?

```matlab
>> Mt = M'

Mt =

     0     0     1     4     1     7
     0     0     2     5     2     8
     0     0     3     6     3     9
     1     7     7    10     4    10
     2     8     8    11     5    11
     3     9     9    12     6    12
```



##### b) Quel est le résultat de la multiplication terme à terme de M par M t ?

```matlab
>> M.*Mt

ans =

     0     0     0     4     2    21
     0     0     0    35    16    72
     0     0     9    42    24    81
     4    35    42   100    44   120
     2    16    24    44    25    66
    21    72    81   120    66   144
```



##### c) Quelles sont les valeurs propres de M ?

```matlab
>> eig(M)

ans =

   35.8676
   -6.6803
    0.9334
   -0.1207
    0.0000
   -0.0000
```



#### 2. Considérons le système linéaire suivant :

$$
\begin{cases} 6x + y - 5z = 10 \\ 2x + 2y + 3z = 11\\ 4x - 9y + 7z = 12 \end{cases}
$$

##### a) Exprimez ce système sous forme matricielle Ax = b

````matlab
>> A=[ 6 1 -5; 2 2 3; 4 -9 7]

A =

     6     1    -5
     2     2     3
     4    -9     7
     
>> b = [10;11;12]

b =

    10
    11
    12
````



##### b) Montrez que ce système admet une solution, en calculant le déterminant de A.

```matlab
>> det(A)

ans =

  374.0000
```



##### c)  En utilisant la puissance de MatLab, déterminez le vecteur x solution de l'équation

```matlab
>> X=A\b

X =

    2.6310
    0.8717
    1.3316
```



##### d) vérifiez la validité de cette solution (en multipliant A par x).

```matlab
>> A*X

ans =

   10.0000
   11.0000
   12.0000
```



### 3.5 Opérateurs logiques

| Operateur    | Symboles                                                 |
| ------------ | -------------------------------------------------------- |
| Relationnels | **<**,**<=**,**>=**,**==** (égalité), **~=** (différent) |
| Logiques     | **&** (et), **\|** (ou), **~** ou **not** (non)          |



#### 1. Créez une matrice M aléatoire à  3 lignes, 7 colonnes (loi uniforme)

```matlab
>> M= rand(3,7)

M =

    0.8147    0.9134    0.2785    0.9649    0.9572    0.1419    0.7922
    0.9058    0.6324    0.5469    0.1576    0.4854    0.4218    0.9595
    0.1270    0.0975    0.9575    0.9706    0.8003    0.9157    0.6557
```

##### a) Construisez la matrice P, où chaque coefficient vaut 1 si le coefficient correspondant de M est inférieur à 0.4, et 0 sinon.

```matlab
>> P=M<0.4

P =

  3×7 logical array

   0   0   1   0   0   1   0
   0   0   0   1   0   0   0
   1   1   0   0   0   0   0
```



##### b) Construisez la matrice Q, égale à la matrice M pour les valeurs comprises dans l'intervalle [0.2, 0.6], et à -1 sinon

```matlab
>> Q1=M>=0.2 & M<=0.6

Q1 =

  3×7 logical array

   0   0   1   0   0   0   0
   0   0   1   0   1   1   0
   0   0   0   0   0   0   0

>> Q=Q1.*M

Q =

         0         0    0.2785         0         0         0         0
         0         0    0.5469         0    0.4854    0.4218         0
         0         0         0         0         0         0         0

>> Q2= not(Q1)

Q2 =

  3×7 logical array

   1   1   0   1   1   1   1
   1   1   0   1   0   0   1
   1   1   1   1   1   1   1

>> Q3=Q2*-1

Q3 =

    -1    -1     0    -1    -1    -1    -1
    -1    -1     0    -1     0     0    -1
    -1    -1    -1    -1    -1    -1    -1

>> Q=Q+Q3

Q =

   -1.0000   -1.0000    0.2785   -1.0000   -1.0000   -1.0000   -1.0000
   -1.0000   -1.0000    0.5469   -1.0000    0.4854    0.4218   -1.0000
   -1.0000   -1.0000   -1.0000   -1.0000   -1.0000   -1.0000   -1.0000


>> Q3=Q2*-1

Q3 =

    -1    -1    -1    -1    -1    -1    -1
    -1    -1    -1    -1     0    -1    -1
    -1    -1    -1     0    -1    -1    -1

>> Q=Q +Q3

Q =

  Columns 1 through 6

   -1.0000   -1.0000   -1.0000   -1.0000   -1.0000   -1.0000
   -1.0000   -1.0000   -1.0000   -1.0000    0.4400   -1.0000
   -1.0000   -1.0000   -1.0000    0.2908   -1.0000   -1.0000

  Column 7

   -1.0000
   -1.0000
   -1.0000
```



#### 2. Créez un vecteur contenant 1000 valeurs binaires, de sorte que 10% de ces valeurs soient des 1.

```matlab
>> Z = rand(1,1000)
%ici les valeurs sont trop grande pour les mettres dans l'exercices
>>Z = Z<0.1
>> sum(Z)

ans =

   110

>> ans/1000

ans =

    0.1100
```



### 3.6 Fonctions usuelles

| Operateur            | Symboles                                                     |
| -------------------- | ------------------------------------------------------------ |
| **max(x)**           | maximum                                                      |
| **min(x)**           | minimum                                                      |
| **sort(x)**          | tri par ordre croissant                                      |
| **[y, I] = sort(x)** | retourne en plus les indices des éléments de **x**           |
| **find(x)**          | retourne les indices non nuls de **x**                       |
| **[y, I] = find(x)** | retourne des lignes (dans le vecteur I) et des colonnes (dans le vecteur J) des éléments non nuls du **x** |
| **sum(x)**           | somme des éléments de **x**                                  |
| **prod(x)**          | produit des éléments de **x**                                |
| **mean(x)**          | moyenne des éléments de **x**                                |
| **std(x)**           | écart type                                                   |



#### 1) Calculez 23!

```matlab
>> V=(1:1:23)

V =

  Columns 1 through 8

     1     2     3     4     5     6     7     8

  Columns 9 through 16

     9    10    11    12    13    14    15    16

  Columns 17 through 23

    17    18    19    20    21    22    23

>> prod(V)

ans =

   2.5852e+22
```



#### 2) Tirez 100 nombres aléatoire de l'intervalle [5, 7] (loi uniforme, centrée sur 6), et stockez les dans un vecteur x.

```matlab
>> x=rand(1,100)
>> x=x*2
>> x=x+5
```

> Note: ici je n'ai pas mis tout les résultats car il y en a trop



##### a) Calculez la moyenne et l'écart type de ces valeurs.

```matlab
>> mean(x)

ans =

    5.9808
```



##### B) Quelle est la valeur minimale du vecteur, et la position du coecient qui la réalise ?

```matlab
>> X=min(x)

X =

    5.0238
```

```matlab
x2=x==Xmin
find(x2)
[y,I]= min(x)
```

> Note: il faut que je demande au prof

##### c) Construisez le vecteur y correspondant aux valeurs entières de x.

Vous utiliserez pour cela la fonction floor

```matlab
>> y = floor(x)

y =

  Columns 1 through 16

     5     6     6     6     6     6     5     6     5     6     5     5     5     5     6     6

  Columns 17 through 32

     5     6     5     5     5     6     6     5     5     5     6     6     6     5     6     6

  Columns 33 through 48

     5     5     5     6     5     6     5     6     5     6     6     6     6     6     5     5

  Columns 49 through 64

     5     6     5     6     5     6     5     5     5     6     5     5     6     6     6     6

  Columns 65 through 80

     5     6     6     5     6     5     5     6     6     6     5     6     5     5     5     5

  Columns 81 through 96

     6     5     6     5     6     5     6     6     6     5     5     5     6     5     6     6

  Columns 97 through 100

     6     5     5     5
```



##### d) Quelle est la proportion de coefficients égaux à 5 dans y ? 

```matlab
>> y2 = y==5

y2 =

  1×100 logical array

  Columns 1 through 24

   1   0   0   0   0   0   1   0   1   0   1   1   1   1   0   0   1   0   1   1   1   0   0   1

  Columns 25 through 48

   1   1   0   0   0   1   0   0   1   1   1   0   1   0   1   0   1   0   0   0   0   0   1   1

  Columns 49 through 72

   1   0   1   0   1   0   1   1   1   0   1   1   0   0   0   0   1   0   0   1   0   1   1   0

  Columns 73 through 96

   0   0   1   0   1   1   1   1   0   1   0   1   0   1   0   0   0   1   1   1   0   1   0   0

  Columns 97 through 100

   0   1   1   1

>> sum(y2)

ans =

    50
```



#### 3. Construisez une matrice M aléatoire à 3 lignes, 7 colonnes (loi uniforme).

```matlab
>> M = randn(3,7)

M =

    2.9080   -1.0582    1.0984   -2.0518   -1.5771    0.0335    0.3502
    0.8252   -0.4686   -0.2779   -0.3538    0.5080   -1.3337   -0.2991
    1.3790   -0.2725    0.7015   -0.8236    0.2820    1.1275    0.0229
```



##### a) Calculez la moyenne et l'écart type de ces valeurs.

```matlab
>> mean(mean(M))

ans =

    0.0343

>> std(std(M))

ans =

    0.3588
```



##### b)  Quelle est la valeur minimale de la matrice, et la position du coefficient qui la réalise ?

```matlab
>> min(M)

ans =

    0.8252   -1.0582   -0.2779   -2.0518   -1.5771   -1.3337   -0.2991

>> min(ans)

ans =

   -2.0518

>> [z,Z] = min(y)

z =

     5


Z =

     1
```



##### c) Combien des coecients de M sont-ils inférieurs à 0.3 ou supérieurs à 0.7 ?

```matlab
>> M2= M<0.3 & M>0.7

M2 =

  3×7 logical array

   0   0   0   0   0   0   0
   0   0   0   0   0   0   0
   0   0   0   0   0   0   0

>> sum(sum(M2))

ans =

     0
```

