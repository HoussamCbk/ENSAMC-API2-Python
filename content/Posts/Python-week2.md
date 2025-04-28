---
title: Python-week1
date: 2025-04-27
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

