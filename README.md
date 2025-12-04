# TP Création de Site Web - Portfolio "Arcade"

## Informations Étudiant
Nom : LAMBERT
Prénom : Simon
Groupe : Groupe 2
Binôme : Seul

## 1. Thème du projet
Pour ce TP, j'ai choisi de réaliser un **Portfolio Personnel** avec une esthétique **Rétro / Arcade**.
L'objectif était de créer une interface immersive rappelant les menus de jeux vidéo, tout en restant une présentation professionnelle de mes compétences et projets (notamment la borne d'arcade présentée dans la page "Projet").

Le design :
* Un effet "Glassmorphism" (fond effet verre flouté).
* Une navigation type "Bento" sur l'accueil.
* Des animations fluides et des interactions sonores/visuelles.

## 3. Difficultés rencontrées et Solutions

Durant le développement, j'ai fait face à plusieurs défis techniques :

* **L'affichage format "Bento" (Grille irrégulière) :**
    *Difficulté :* Créer une mise en page dynamique où les éléments ont des tailles différentes (certains carrés, d'autres rectangulaires) tout en restant parfaitement alignés.
    *Solution :* J'ai utilisé **CSS Grid**. J'ai défini une grille de base avec 4 colonnes (`grid-template-columns: repeat(4, 1fr)`). Pour les éléments plus grands, j'ai créé des classes spécifiques (`.large`, `.wide`) qui utilisent la propriété `span` (ex: `grid-column: span 2`) pour fusionner plusieurs cellules.
     **Conflit de règles CSS (La Cascade) :**
         *Difficulté :* Sur la version mobile, ma vidéo refusait de s'agrandir et restait bloquée à 30% de largeur, malgré ma règle `width: 100%` dans la Media Query.
         *Solution :* J'ai compris que l'ordre du code est crucial. Ma règle générale (30%) était écrite *après* ma Media Query dans le fichier CSS, elle écrasait donc la règle mobile. J'ai résolu le problème en déplaçant les styles généraux avant les `@media`, respectant ainsi l'ordre de lecture du navigateur.
    
## 2. Structure des fichiers
Voici l'organisation du dossier rendu :

```text
lambert-simon_groupe[X]/
├── index.html          # Page d'accueil (Menu principal & Bento)
├── projet.html         # Page de présentation de la Borne d'Arcade (Vidéo + Tableau)
├── contact.html        # Page de formulaire de contact (sans envoye de données ou stockées)
├── README.md           # Ce fichier explicatif
├── css/
│   └── style.css       # Feuille de style unique (variables, responsive, animations)
├── img/
│   ├── background.svg  # Fond d'écran principal image vectorielle
│   └── arcade.svg      # Visuel du projet SolidWorks image vectorielle
├── audio/
│   └── audio.mp3       # Ambiance sonore du site
└── video/
    └── project_demo.mp4 # Vidéo de démonstration du projet
