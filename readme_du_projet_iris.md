# 🌸 À la découverte des données Iris

Projet d'exploration visuelle, d'analyse statistique et de réduction de dimensionnalité réalisé dans le cadre du cours de **Visualisation des données massives et hétérogènes** (Master 1 Data Science — **École Nationale Supérieure Polytechnique de Yaoundé - ENSPY**).

---

## 📋 Présentation du projet

L'objectif de ce projet est d'explorer le célèbre jeu de données **`iris`** (collecté par le botaniste Edgar Anderson et popularisé par Ronald Fisher en 1936). Ce tableau contient les mesures morphologiques (en centimètres) de **150 fleurs** réparties équitablement en **3 espèces** (*setosa*, *versicolor*, *virginica*).

À travers une démarche progressive en **R**, nous cherchons à répondre à trois questions directrices :
* Quelles mesures distinguent le mieux les espèces ?
* Quelles variables évoluent ensemble ?
* Peut-on résumer les 4 mesures en 2 dimensions sans perdre l'essentiel ?

---

## 🛠️ Technologies et packages utilisés

L'intégralité du code, des graphiques et du rapport a été développée en **R** sous format **Quarto (`.qmd`)**.

**Bibliothèques principales :**
* Manipulation de données : `dplyr`, `tidyr`, `tibble`, `purrr`, `tidyverse`
* Visualisation : `ggplot2`, `patchwork`
* Statistiques & ACP : `stats` (`aov`, `kruskal.test`, `cor.test`, `prcomp`)

---

## 🧭 Démarche méthodologique

1. **Compréhension et préparation des données** : Vérification de la structure (150 lignes, 5 colonnes), gestion des valeurs manquantes (0) et analyse d'un doublon conservé car cohérent avec l'arrondi au millimètre.
2. **Exploration visuelle** :
   * *Univariée* : Histogrammes et courbes de densité par espèce.
   * *Bivariée* : Boîtes à moustaches (boxplots) et nuages de points avec régressions linéaires.
   * *Multivariée* : Matrices de nuages de points et heatmaps de corrélation (globales et intra-espèces).
3. **Tests statistiques** : Validation des écarts entre espèces via l'**ANOVA**, le **test de Welch** et le **test de Kruskal-Wallis**, accompagnés de tests de corrélation de **Pearson**.
4. **Analyse en Composantes Principales (ACP)** : Réduction de dimension (centrée-réduite), éboulis des valeurs propres, cercle des corrélations, plan factoriel et biplot.
5. **Classification** : Évaluation de la séparabilité des groupes via une **Analyse Discriminante Linéaire (ADL)**.

---

## 🔍 Principaux résultats

* **Le pouvoir discriminant des pétales** : `Petal.Length` et `Petal.Width` sont très fortement corrélées ($r \approx 0,96$) et expliquent à elles seules près de 94 % de la variance liée à l'espèce ($\eta^2 \approx 0,94$).
* **Une espèce isolée** : *Setosa* se distingue nettement des deux autres espèces sur presque toutes les représentations, tandis que *versicolor* et *virginica* sont proches mais séparables.
* **Le paradoxe de Simpson** : Sur l'ensemble du jeu de données, la longueur et la largeur des sépales semblent non corrélées ($r \approx -0,12$), mais la corrélation devient nettement positive lorsqu'on observe chaque espèce séparément.
* **Résumé en 2 dimensions (ACP)** : Les deux premiers axes principaux (**PC1** et **PC2**) conservent **95,8 % de l'information** totale et permettent de retrouver naturellement les trois groupes d'espèces sans que l'algorithme n'ait connaissance des étiquettes.
* **Performance de classification** : L'analyse discriminante linéaire permet de reclasser correctement **98 % des fleurs** (147 sur 150).

---

## 🚀 Comment exécuter le projet

1. Cloner ce dépôt sur votre machine locale :
   ```bash
   git clone <url-de-votre-depot>
   ```
2. Ouvrir le fichier `.qmd` dans **RStudio** (ou VS Code avec l'extension Quarto).
3. S'assurer que les packages du `tidyverse` et `patchwork` sont installés :
   ```r
   install.packages(c("tidyverse", "patchwork"))
   ```
4. Cliquer sur **Render** (ou exécuter `quarto render votre_fichier.qmd`) pour générer le rapport complet.

---

## 👥 Équipe projet (ENSPY - Master 1 Data Science)

* **ASSABDJEU NGUEDON Syntiche Junelle** 
* **ZANGUIM TEMATIO Darelle** 
* **NGO KAMLA Eleanore Megane** 
* **TCHONKAHUI FOTSO Guy Landry** 
* **MOUAFO FOTSING Franck Aldrick** 
* **MEFO EVINA Celestin** 