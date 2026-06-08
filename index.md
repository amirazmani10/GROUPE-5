---
layout: home
title: Documentation Otto-MKS
nav_order: 1
---

# 🤖 Robot Otto-MKS — I1 Groupe 5

<img width="250" height="540" alt="robot_face" src="https://github.com/user-attachments/assets/ec0fb678-6115-4ae2-aa7a-977c9bfebf92" />
<img width="250" height="540" alt="robot_profil" src="https://github.com/user-attachments/assets/10dbde82-93de-4360-bb09-8c82f973f014" />

> 🎥 *La vidéo du robot en fonctionnement est disponible dans le document Word (elle ne peut pas être intégrée ici).*



**Robot humanoïde bipède autonome**  
UniLaSalle Amiens — École d'ingénieurs Énergie & Numérique  
Année universitaire **2025-2026**

---

## 👥 Équipe

- Ilyas Nassiri
- Amir Azmani
- Noé Obame

### Résultat obtenu

🏅 **5ᵉ place aux Ottolympiades**

**Point fort identifié :** vitesse de déplacement.

[Voir le 3D](https://cad.onshape.com/documents/07646ee59cb8562e28d77f4a/w/f8c3c05c39bbff21b5297472/e/8cb9828b3fc7f4771eeacd2e?renderMode=0&uiState=6a26caec1c9cfda4dc6e792d){: .btn .btn-blue }

---

# Introduction

Dans le cadre du projet MakerSpace de première année à UniLaSalle Amiens, notre équipe a conçu, assemblé, programmé et optimisé un robot humanoïde bipède basé sur la plateforme open-source Otto-MKS.

L'objectif du projet était de développer un robot capable de se déplacer de manière autonome tout en relevant différents défis techniques lors des Ottolympiades. Au-delà de l'aspect ludique et compétitif, ce projet nous a permis de découvrir l'ensemble de la chaîne de conception d'un système embarqué : modélisation, fabrication, électronique, programmation et validation expérimentale.

Contrairement à une simple reproduction du modèle de base, nous avons choisi d'agrandir le robot afin d'améliorer ses performances en déplacement. Cette décision a nécessité un important travail d'adaptation mécanique et logicielle.

Le projet nous a permis d'appliquer concrètement plusieurs notions d'ingénierie tout en développant notre capacité à travailler en équipe et à résoudre des problèmes techniques complexes.

---

# I. Présentation du projet

## Contexte

Le robot Otto-MKS est une plateforme robotique open-source destinée à l'apprentissage de la programmation, de l'électronique et de la robotique.

Le projet s'inscrit dans les activités du MakerSpace de l'école, un espace dédié à la fabrication numérique et au prototypage rapide. L'objectif pédagogique est de permettre aux étudiants de concevoir un système robotique complet tout en découvrant les contraintes réelles d'un projet d'ingénierie.

Notre équipe a choisi d'aller plus loin que le modèle standard en développant une version agrandie du robot afin d'améliorer sa vitesse de déplacement et ses performances lors de la compétition.

## Objectifs

Les principaux objectifs du projet étaient :

- Concevoir un robot bipède entièrement fonctionnel ;
- Comprendre l'architecture matérielle d'un système embarqué ;
- Programmer un microcontrôleur ESP32-C3 ;
- Développer une marche rapide et stable ;
- Intégrer un système de détection d'obstacles ;
- Exploiter l'impression 3D pour personnaliser la structure ;
- Participer aux Ottolympiades avec un robot performant.

## Architecture générale

Le robot repose sur une architecture simple composée de trois niveaux :

### Entrées

- Capteur ultrason HC-SR04 ;
- Commandes Bluetooth depuis un smartphone.

### Traitement

- Carte Otto-MKS équipée d'un ESP32-C3.

### Sorties

- Quatre servomoteurs ;
- Buzzer intégré.

Cette architecture permet un fonctionnement autonome ou télécommandé selon les besoins.

---

# II. Matériel et composants

| Composant | Quantité | Fonction |
|-----------|-----------|-----------|
| Carte OTTO-MKS (ESP32-C3) | 1 | Contrôle général du robot |
| Servomoteurs 9g | 4 | Déplacement des jambes et des pieds |
| HC-SR04 | 1 | Détection d'obstacles |
| Batterie 9V | 1 | Alimentation autonome |
| Câble USB-C | 1 | Programmation et tests |

## Carte électronique

La carte Otto-MKS constitue le cerveau du robot.

Elle intègre un microcontrôleur ESP32-C3 permettant :

- Le contrôle des servomoteurs ;
- La gestion des capteurs ;
- La communication Bluetooth ;
- Le traitement des données ;
- La gestion de l'alimentation.

## Servomoteurs

Les quatre servomoteurs assurent l'ensemble des mouvements du robot.

Deux moteurs contrôlent les jambes tandis que deux autres assurent l'inclinaison des pieds afin de maintenir l'équilibre pendant la marche.

La précision de leur synchronisation est essentielle pour garantir la stabilité du robot.

## Capteur HC-SR04

Le capteur ultrason HC-SR04 mesure la distance entre le robot et les obstacles présents sur son trajet.

Cette information permet d'envisager la mise en place d'un système d'évitement automatique et d'améliorer l'autonomie du robot.

---

# III. Conception et assemblage

## Impression 3D

Toutes les pièces du robot ont été fabriquées grâce à l'impression 3D :

- Tête ;
- Tronc ;
- Jambes ;
- Pieds.

Une fois les pièces imprimées, elles ont été nettoyées, ébavurées puis vérifiées afin d'assurer un assemblage correct.

### Choix d'agrandissement

Notre principal choix technique a été d'augmenter les dimensions du robot.

L'objectif était d'obtenir :

- Une plus grande longueur d'enjambée ;
- Une meilleure vitesse de déplacement ;
- Un avantage compétitif lors des épreuves.

Cependant, cette modification a également entraîné plusieurs contraintes :

- Augmentation du poids ;
- Sollicitations mécaniques plus importantes ;
- Risque accru de perte d'équilibre.

## Assemblage mécanique

L'assemblage s'est déroulé en plusieurs étapes :

1. Montage du châssis ;
2. Installation des servomoteurs ;
3. Assemblage des jambes ;
4. Montage des pieds ;
5. Vérification des alignements.

Une attention particulière a été portée à la réduction des jeux mécaniques afin d'améliorer la stabilité du robot.

## Câblage électronique

Le câblage a été réalisé avec soin afin de garantir la fiabilité du système.

Chaque connexion a été vérifiée avant les phases de test afin d'éviter les erreurs de fonctionnement ou les risques de détérioration du matériel.

---

# IV. Programmation

## Environnement de développement

Le programme a été développé sous **Arduino IDE** en langage **C/C++**.

Le code est compilé puis téléversé sur l'ESP32-C3 via une connexion USB-C.

## Adaptation à la nouvelle taille du robot

L'agrandissement du robot a nécessité une recalibration complète des paramètres de marche.

Les réglages ont porté sur :

- Les angles de servomoteurs ;
- Les amplitudes de mouvement ;
- Les délais d'exécution ;
- Les paramètres d'équilibrage.

De nombreux essais ont été réalisés afin de trouver le meilleur compromis entre vitesse et stabilité.

## Fonctionnalités développées

### Marche avant

Fonction principale utilisée lors des épreuves.

### Marche arrière

Permet de corriger la trajectoire du robot.

### Rotation

Le robot peut effectuer :

- Des rotations à gauche ;
- Des rotations à droite.

### Contrôle Bluetooth

Grâce à l'application RemoteXY :

- Pilotage à distance ;
- Contrôle via joystick ;
- Mode manuel ;
- Mode automatique.

### Détection d'obstacles

Le capteur HC-SR04 a été intégré au système afin de préparer le développement d'un comportement autonome.

## Difficultés rencontrées

### Synchronisation des servomoteurs

La coordination des quatre servomoteurs représentait le principal défi du projet.

Des réglages incorrects provoquaient :

- Des oscillations ;
- Des pertes d'équilibre ;
- Des chutes.

### Calibration

Chaque modification mécanique imposait de nouveaux réglages logiciels.

Les paramètres du robot standard n'étaient plus adaptés à notre version agrandie.

### Mesures incohérentes

Le capteur HC-SR04 produisait parfois des mesures erronées.

Des filtres logiciels ont donc été ajoutés afin d'améliorer la fiabilité des données.

---

# V. Résultats — Journée des challenges

Les performances observées lors des Ottolympiades ont validé nos choix techniques.

Notre robot s'est particulièrement distingué par sa rapidité de déplacement.

| Classement | Point fort |
|------------|------------|
| 🏅 5ᵉ place | Vitesse de déplacement |

## Analyse des performances

### Vitesse

L'agrandissement du robot a permis d'obtenir des foulées plus longues et donc une vitesse supérieure à celle de nombreuses équipes concurrentes.

### Stabilité

Malgré sa taille plus importante, le robot est resté globalement stable grâce aux nombreux ajustements réalisés sur les paramètres de marche.

### Fiabilité

Le système a fonctionné correctement durant l'ensemble des épreuves sans défaillance majeure.

## Livrables

- Robot fonctionnel présenté aux Ottolympiades ;
- Documentation technique ;
- Modèle OnShape modifié ;
- Vidéo de démonstration.

---

# VI. Bilan et améliorations

Ce projet nous a permis de développer des compétences en :

- Programmation embarquée ;
- Électronique ;
- Conception mécanique ;
- Impression 3D ;
- Gestion de projet ;
- Travail en équipe.

## Améliorations envisagées

### Détection d'obstacles

- Ajout d'un second capteur ;
- Couverture latérale améliorée.

### Contrôle Bluetooth

- Modification des paramètres de marche en temps réel ;
- Interface utilisateur enrichie.

### Gestion de l'énergie

- Batterie plus performante ;
- Réduction de la consommation électrique.

### Mécanique

- Renforcement des assemblages ;
- Réduction des jeux mécaniques.

### Intelligence embarquée

- Auto-calibration ;
- Évitement autonome avancé ;
- Adaptation automatique au terrain.

---
# VII. Code source

Le programme principal du robot a été développé en langage **C/C++** sous **Arduino IDE** puis téléversé sur la carte **Otto-MKS équipée d'un ESP32-C3**.

Le code assure :

- Le contrôle des quatre servomoteurs ;
- La marche avant et arrière ;
- Les rotations gauche et droite ;
- Le pilotage Bluetooth via RemoteXY ;
- Le mode manuel et le mode automatique ;
- La calibration des mouvements ;
- L'initialisation du robot.

## Bibliothèques utilisées

- ESP32Servo
- RemoteXY
- BLEDevice
- Arduino
- notes.h

## Paramètres principaux

| Paramètre | Description |
|------------|------------|
| `tempo` | Vitesse d'exécution des pas |
| `stride` | Amplitude des mouvements |
| `liftGauche` | Levée du pied gauche |
| `liftDroite` | Levée du pied droit |
| `drift` | Correction de trajectoire |

Ces paramètres ont été ajustés tout au long du projet afin d'adapter les mouvements à la version agrandie du robot.

## Consulter le programme

Le code source complet est disponible dans le fichier suivant :

➡️ [Accéder au programme complet](code/main.ino)

Le fichier contient l'ensemble des fonctions de déplacement, de communication Bluetooth et de contrôle des servomoteurs utilisées lors des Ottolympiades.
# VIII. Code source

Le programme principal `main.ino` assure :

- Le contrôle des servomoteurs ;
- Les déplacements du robot ;
- Le pilotage Bluetooth ;
- La gestion des paramètres de marche ;
- Les fonctions d'initialisation.

## Bibliothèques utilisées

- ESP32Servo
- RemoteXY
- BLEDevice
- notes.h

L'ensemble du code a été développé et testé sous Arduino IDE avant son déploiement sur l'ESP32-C3.

---

# Conclusion

Le projet Otto-MKS a constitué une expérience complète de conception et d'intégration d'un système robotique autonome.

Depuis l'impression 3D jusqu'à la compétition finale, chaque étape nous a permis d'acquérir de nouvelles compétences techniques et méthodologiques.

La cinquième place obtenue aux Ottolympiades valide les choix réalisés par l'équipe, notamment l'agrandissement du robot et l'optimisation des paramètres de marche. Cette expérience constitue une base solide pour de futures améliorations visant à rendre le robot encore plus autonome, performant et intelligent.
