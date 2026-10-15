# 🎯 Optimisation du Problème Vertex Cover (Couverture par Sommets)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg?logo=python)](https://www.python.org/)
[![Complexity](https://img.shields.io/badge/Complexity-NP--Hard-red.svg)](https://en.wikipedia.org/wiki/Vertex_cover)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Ce projet propose une étude algorithmique approfondie, théorique et expérimentale, du problème classique de la **Couverture par Sommets** (*Minimum Vertex Cover*), un problème fondamental **NP-difficile** de la théorie des graphes.

---

## 📌 Présentation du Problème

Pour un graphe non orienté $G = (V, E)$, une **couverture par sommets** est un sous-ensemble $C \subseteq V$ tel que pour chaque arête $(u, v) \in E$, au moins une des extrémités $u$ ou $v$ appartient à $C$.

L'objectif d'optimisation consiste à trouver une couverture $C$ de **taille minimale** $|C|$.

---

## ⚡ Algorithmes Implémentés

Le module [`graphe.py`](graphe.py) propose une suite complète de méthodes exactes et heuristiques :

### 1. Algorithmes Approchés
- **Heuristique Gloutonne (`algo_glouton`)** :
  Sélectionne à chaque itération le sommet de degré maximal dans le sous-graphe courant jusqu'à couvrir toutes les arêtes.
- **2-Approximation par Couplage Maximal (`algo_couplage`)** :
  Construit un couplage maximal $M$ en ajoutant répétitivement les deux extrémités d'une arête sélectionnée arbitrairement. Garantit un ratio d'approximation de $2$.

### 2. Algorithmes Exacts (Branch & Bound)
- **Branch & Bound Standard (`algo_branchement`)** :
  Exploration arborescente exhaustive avec élagage par branchement binaire sur une arête $(u, v)$ (soit $u \in C$, soit $v \in C$).
- **Branch & Bound Amélioré avec Bornes Inférieures (`algo_branchement_bornes_upg`)** :
  Élagage hautement optimisé calculant une borne inférieure basée sur un couplage maximal pour éliminer les sous-arbres stériles avant toute exploration récursive.

---

## 📊 Évaluation Expérimentale & Benchmarks

Le projet intègre un banc de tests automatisé générant des graphes aléatoires d'Erdős-Rényi $G(n, p)$ afin de mesurer :
- Les **temps d'exécution** en fonction du nombre de sommets $n$ et de la densité $p$.
- Les **ratios d'approximation effectifs** par rapport aux solutions optimales exactes.
- La génération de visualisations comparatives à l'aide de **Matplotlib**.

---

## 🚀 Utilisation

### Prérequis
```bash
pip install matplotlib numpy
```

### Exécution
```bash
python3 graphe.py
```

### Format des instances de graphes (`.txt`)
Le chargeur prend en charge un format textuel standard :
```text
Sommets
A
B
C
Aretes
A B
B C
```

---

## 👥 Auteur
- **Radouane Aouini**
