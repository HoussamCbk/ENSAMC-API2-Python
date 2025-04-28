---
title: Python-week2
date: 2025-04-28
author: CHOUBIK Houssam
draft: false
tags:
  - Python
  - ENSAMC
---

Les types de variables :
On a deux types de variables , variable **locale** et variable **globale**.
- Les variables locales sont propres à la fonction.
- Les variables globales sont définies à l'extérieur de la fonction et peuvent être utiliser par n'importe quelle fonction.

Exemple de **variable locale** :
```python
def ma_fonction():
x = 10 # Variable locale
print("Dans la fonction, x =", x)
ma_fonction() # Affiche la valeur x
```

Exemple de **variable globale**
```python
y = 20 # Variable globale
def ma_fonction():
print("Dans la fonction, y =", y)
ma_fonction() # Affiche : Dans la fonction, y = 20
print("En dehors de la fonction, y =", y) # Affiche : En dehors de la fonction, y = 20
```

 ## TP3
 Exercice 1 : 
 **Enoncé :**
 Menu d'Options avec Fonctions, match et Boucles
	1- Saisie de l'utilisateur : Demandez à l'utilisateur de saisir un nombre entier positif. Gérez les cas d'erreur, par exemple, si l'utilisateur saisit un nombre négatif ou une entrée non valide, en utilisant une boucle FAIRE … TANQUE.
	2- Affichage du Menu : Affichez un menu offrant les options suivantes, en plus d'une option pour quitter :
		A. Vérifier et afficher si le nombre est un nombre premier.
		B. Tester si un entier donné en entrée est pair ou impair.
		C. Convertir un nombre décimal non négatif en base b (où b est également saisi par l'utilisateur).
		D. Calculer la factorielle d’un entier non négatif donné en entrée.
		Q. Quitter le menu.
	3- Création de Fonctions : Pour chaque action du menu, créez une fonction distincte :
		A. est_premier(nombre)
		B. est_pair_impair(nombre)
		C. convertir_base(nombre, base)
		D. calculer_factorielle(nombre)
	4- Traitement du Choix :Utilisez match pour exécuter le bloc de code spécifique selon l'option choisie par l'utilisateur. Assurez-vous d'appeler la fonction correspondante en fonction du choix.
	5- Boucle Continue : Le programme doit continuer à exécuter, affichant le menu après chaque action, jusqu'à ce que l'utilisateur choisisse de quitter le programme (utiliser la boucle FAIRE … TANQUE).
	
**Corrigé :**
```python
def est_premier(nombre):

    if nombre > 1:

        for i in range(2, nombre):

            if nombre % i == 0:

                return 0

        return 1

    else:

        return 0

def est_pair_impair(nombre):

    if nombre % 2 == 0:

        return "pair"

    else:

        return "impair"

def convertir_base(nombre, base):  

    if base < 2 or base > 9:

        raise ValueError("La base doit être 2<=b<=9.")

    binaire = ""

    nb = nombre

    if nb == 0:

        binaire = "0"

    else:

        while nb > 0:

            binaire = str(nb % base) + binaire

            nb = nb // base  

    return binaire

def fact(nombre):

    if nombre < 0:

        raise ValueError("La factorielle n'est pas définie pour les nombres négatifs.")

    if nombre == 0:

        return 1

    else:

        f = 1

        for i in range(1, nombre + 1):

            f = f * i

        return f

  
  

while True:

    x=int(input("Veuillez saisir un entier positif : "))

    if x >0:

        break

  

print("Pour activer le menu, veuillez tapez 1.")

m=int(input())

choice=0

while choice!=5:

    if m==1:

        print("Menu :")

        print("1. Vérifier et afficher si le nombre est un nombre premier.")

        print("2. Tester si un entier donné en entrée est pair ou impair.")

        print("3. Convertir un nombre décimal non négatif en base b (où b est également saisi par l'utilisateur).")

        print("4. Calculer la factorielle d’un entier non négatif donné en entrée.")

        print("5. Quitter le menu.")

        print("Veuillez choisir une option.")

        choice=int(input())

        match choice:

            case 1:

                if est_premier(x):

                    print(f"{x} est un nombre premier.")

                else:

                    print(f"{x} n'est pas un nombre premier.")

            case 2:

                pair_impair = est_pair_impair(x)

                print(f"{x} est un nombre {pair_impair}.")

            case 3:

                b = int(input("Veuillez saisir la base (supérieure ou égale à 2) : "))

                try:

                    binaire = convertir_base(x, b)

                    print(f"Le nombre {x} en base {b} est : {binaire}")

                except ValueError as e:

                    print(e)

            case 4:

                try:

                    f = fact(x)

                    print(f"La factorielle de {x} est : {f}")

                except ValueError as e:

                    print(e)

            case 5:

                print("Au revoir !")

            case _:

                print("Erreur : option invalide.")
```
	