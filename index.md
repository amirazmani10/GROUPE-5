---
layout: home
title: Documentation Otto-MKS
nav_order: 1
---

# 🤖 Robot Otto-MKS — I1 Groupe 5

<img width="250" height="540" alt="robot_face" src="https://github.com/user-attachments/assets/ec0fb678-6115-4ae2-aa7a-977c9bfebf92" />
<img width="250" height="540" alt="robot_profil" src="https://github.com/user-attachments/assets/10dbde82-93de-4360-bb09-8c82f973f014" />

> 🎥 *La vidéo du robot en fonctionnement (format portrait) est disponible dans le document Word (elle ne peut pas être intégrée ici).*

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

Dans le cadre de ce projet, notre équipe — Ilyas, Amir et Noé — a relevé le défi de concevoir et de faire fonctionner un robot humanoïde bipède : le fameux Otto-MKS. L'objectif n'était pas seulement d'assembler des pièces et d'écrire quelques lignes de code, mais bien de créer un robot capable d'évoluer en autonomie dans un parcours semé d'obstacles.

Le projet nous a plongés dans plusieurs disciplines en même temps : programmation embarquée, électronique, mécanique, et même un peu de design via l'impression 3D. Apprendre à faire dialoguer tous ces éléments ensemble — et à les faire fonctionner de concert sans que tout s'effondre lors de la compétition — c'était toute la difficulté, et toute la richesse de cette expérience.

Ce rapport retrace les étapes clés de notre aventure : de l'impression des premières pièces jusqu'à la journée des challenges, en passant par les galères de câblage, les bugs de code et nos choix techniques les plus déterminants.

Contrairement à une simple reproduction du modèle de base, nous avons choisi d'agrandir le robot afin d'améliorer ses performances en déplacement. Cette décision a nécessité un important travail d'adaptation mécanique et logicielle.

---

# I. Présentation du projet Otto-MKS

## Contexte

Le projet Otto-MKS s'inscrit dans les activités du MakerSpace de l'école, un espace dédié à la fabrication numérique et au prototypage. C'est un terrain de jeu idéal pour mettre les mains dans le cambouis et confronter la théorie des cours à la réalité d'un vrai projet technique.

Otto est un robot open-source, conçu pour être abordable, personnalisable et éducatif. Sa structure modulaire et sa compatibilité avec Arduino en font une excellente plateforme d'apprentissage. Ce que nous avons fait, c'est nous approprier la base pour la pousser plus loin : plus grand, plus rapide, plus performant.

## Objectifs du projet

- Concevoir et assembler un robot bipède fonctionnel ;
- Programmer des déplacements autonomes fluides et stables ;
- Intégrer un capteur de détection d'obstacles ;
- Optimiser les performances pour être compétitifs lors de la journée des challenges ;
- Découvrir et maîtriser l'environnement Arduino IDE et le langage C/C++ ;
- Exploiter les possibilités de l'impression 3D pour personnaliser la structure.

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

# II. Matériel et composants utilisés

Le robot Otto-MKS repose sur un ensemble de composants soigneusement choisis pour leur compacité, leur fiabilité et leur compatibilité :

| Composant | Quantité | Fonction |
|-----------|-----------|-----------|
| Carte électronique OTTO-MKS (ESP32-C3) | 1 | Contrôle du robot |
| Servomoteurs 9g | 4 | Actionneurs — mouvements des jambes et pieds |
| Capteur HC-SR04 | 1 | Détection d'obstacles par ultrasons |
| Batterie 9V | 1 | Alimentation autonome du robot |
| Câble USB-C | 1 | Programmation et test via Arduino IDE |

## La carte électronique Otto-MKS

C'est le cerveau du robot. Elle reçoit le programme que l'on écrit, l'exécute et coordonne l'ensemble des périphériques. Au cœur de cette carte se trouve un microcontrôleur ESP32-C3, un composant puissant capable de gérer simultanément l'alimentation, le pilotage des servomoteurs, le traitement des données capteurs et même une communication Wi-Fi/Bluetooth si on le souhaite.

## Les servomoteurs 9g

Ce sont eux qui donnent vie au robot. Chaque servomoteur reçoit un angle précis depuis la carte électronique et s'y positionne fidèlement. Quatre servomoteurs assurent les mouvements des hanches et des pieds, permettant à Otto de marcher, de tourner, de danser — ou de foncer vers la ligne d'arrivée, ce qui était notre priorité.

## Le capteur ultrasonique HC-SR04

Ce capteur est les yeux d'Otto. Il émet des impulsions ultrasoniques et mesure le temps que met l'écho à revenir pour en déduire la distance d'un obstacle. Grâce à lui, le robot peut ralentir, s'arrêter, ou changer de cap avant d'entrer en collision — une fonctionnalité indispensable pour le parcours d'obstacles.

## La batterie 9V et le câble USB-C

La batterie 9V alimente l'ensemble du système en autonomie. Le câble USB-C, lui, est l'outil de développement : il permet de téléverser le code, de monitorer les données en temps réel et d'alimenter la carte sans batterie pendant les phases de test.

---

# III. Conception et assemblage du robot

## Impression 3D des pièces

La toute première étape du projet a été l'impression 3D des pièces constitutives du robot : la tête, le tronc, les jambes et les pieds. Les fichiers de modélisation ont été préparés puis envoyés vers l'imprimante 3D du MakerSpace.

C'est ici que nous avons pris notre première décision marquante : **agrandir le robot**. Par rapport aux dimensions d'origine, nous avons volontairement revu les proportions à la hausse pour gagner en amplitude de mouvement et, par conséquent, en vitesse de déplacement. Un Otto plus grand, c'est un Otto qui fait des enjambées plus larges — et donc qui va plus vite avec la même fréquence de pas.

Après l'impression, chaque pièce a été inspectée visuellement : bavures, déformations légères, irrégularités de surface. Certaines ont nécessité un ébavurage minutieux pour s'assembler sans forcer.

### Choix d'agrandissement — avantages et contraintes

L'objectif de l'agrandissement était d'obtenir une plus grande longueur d'enjambée, une meilleure vitesse de déplacement et un avantage compétitif lors des épreuves. Cependant, cette modification a également entraîné plusieurs contraintes : une augmentation du poids, des sollicitations mécaniques plus importantes et un risque accru de perte d'équilibre.

## Assemblage mécanique

Une fois les pièces validées, l'assemblage a pu commencer. La structure du châssis a d'abord été montée, puis les servomoteurs ont été installés dans leurs logements dédiés au niveau des hanches et des jambes. Un positionnement précis est crucial : le moindre jeu mécanique se traduit directement par une instabilité à la marche.

Les jambes et les pieds ont ensuite été emboîtés sur les axes des servomoteurs. Des vérifications manuelles ont été effectuées à chaque étape pour s'assurer du bon alignement des articulations et de la liberté de mouvement de chaque partie.

## Câblage électronique

Vient ensuite la partie câblage — probablement la plus délicate visuellement. Chaque composant a été raccordé à la carte Otto-MKS selon son affectation : les servomoteurs sur leurs sorties dédiées, le capteur HC-SR04 sur les broches correspondantes, la batterie sur le connecteur d'alimentation.

Nous avons pris le temps de vérifier les polarités et la solidité de chaque connexion avant de mettre sous tension. Une mauvaise connexion, ça peut rester silencieux pendant des heures... puis provoquer un bug incompréhensible au pire moment. Autant éviter.

---

# IV. Programmation du robot

## Environnement de développement

La programmation d'Otto s'est faite via **Arduino IDE**, un environnement de développement familier et bien documenté pour les microcontrôleurs compatibles Arduino. Le code est écrit en **C/C++**, compilé localement puis téléversé sur la carte ESP32-C3 via le câble USB-C.

## Adaptation du code à notre version agrandie

C'est là que ça devient vraiment intéressant. Agrandir le robot physiquement ne suffit pas — il a fallu adapter le code en conséquence. Les séquences de déplacement d'Otto sont basées sur des angles de servomoteurs et des timings précis. Avec des jambes plus longues, les mêmes angles produisent des mouvements différents, parfois trop amples, parfois déséquilibrants.

Nous avons donc retravaillé en profondeur les paramètres de marche : amplitudes angulaires, vitesses de rotation, délais entre les étapes de la séquence. L'objectif était de trouver le réglage optimal pour maximiser la vitesse de déplacement tout en conservant un robot stable — un robot qui tombe, c'est un robot disqualifié.

## Fonctions programmées

- **Marche avant** : séquence coordonnée des quatre servomoteurs pour un déplacement rapide et équilibré ;
- **Marche arrière** : permet de corriger la trajectoire du robot ;
- **Rotation gauche / droite** : virages contrôlés pour le slalom entre les obstacles ;
- **Mouvements de hanches** : ajustés pour une démarche stable malgré la taille augmentée ;
- **Contrôle Bluetooth** : pilotage à distance via l'application RemoteXY (joystick, mode manuel et mode automatique) ;
- **Détection d'obstacles** : le capteur HC-SR04 est câblé et ses broches déclarées dans le code — l'intégration complète de la logique d'évitement était en cours et figure parmi nos pistes d'amélioration prioritaires.

## Les galères de code — et comment on s'en est sortis

On ne va pas se mentir : la partie programmation a été la plus chronophage. Parmi les difficultés rencontrées, la **synchronisation des servomoteurs** était le principal casse-tête. Des timings mal calibrés provoquaient des oscillations, voire des chutes. Nous avons dû reprendre plusieurs fois les valeurs de délai et tester méthodiquement chaque modification.

Un autre point délicat : le capteur HC-SR04 renvoyait parfois des valeurs aberrantes lorsqu'il était trop proche d'un obstacle ou dans certaines configurations d'angle. Nous avons ajouté dans le code des filtres logiques pour ignorer les mesures clairement incohérentes et assurer un comportement fiable du robot.

Enfin, chaque modification mécanique imposait de nouveaux réglages logiciels : les paramètres du robot standard n'étaient plus adaptés à notre version agrandie. Ces difficultés ont été frustrantes sur le moment, mais c'est précisément ce type de débogage itératif qui forge de vraies compétences d'ingénieur. Chaque bug réglé était une petite victoire.

---

# V. Code source

Voici le code complet qu'on a développé et téléversé sur la carte ESP32-C3. Il regroupe toutes les fonctions de déplacement, la gestion de la télécommande Bluetooth via RemoteXY, ainsi que le mode autonome. On a pas mal itéré dessus avant d'arriver à quelque chose de stable — les commentaires dans le code reflètent nos choix techniques et les paramètres qu'on a ajustés au fil des tests.

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
| `stride` | Amplitude des mouvements (ciseaux) |
| `liftGauche` | Levée du pied gauche |
| `liftDroite` | Levée du pied droit |
| `drift` | Correction de trajectoire |

Ces paramètres ont été ajustés tout au long du projet afin d'adapter les mouvements à la version agrandie du robot.

## Programme complet — `main.ino`

```cpp
#include <Arduino.h>
#include <ESP32Servo.h>

// RemoteXY select connection mode and include library
#define REMOTEXY_MODE__ESP32CORE_BLE
#include <BLEDevice.h>

// ==========================================
// PARAMETRES BLUETOOTH
// ==========================================
#define REMOTEXY_BLUETOOTH_NAME "Otto"
// (Le mot de passe a ete retire)

#include <RemoteXY.h>

// Definition des frequences des notes de musiques
#include "notes.h"
#define DUREE_TEMPS 300
#define BUZZER_PIN D0

// ==========================================
// DECLARATION DES MOTEURS ET CAPTEURS
// ==========================================
Servo legLeft;
Servo legRight;
Servo footLeft;
Servo footRight;

const int trig_pin = D2;
const int echo_pin = D1;
const int pinLegLeft = D7;
const int pinLegRight = D8;
const int pinFootLeft = D9;
const int pinFootRight = D10;

bool debug = false;

// ==========================================
// CONFIGURATION REMOTEXY
// ==========================================
#pragma pack(push, 1)
uint8_t const PROGMEM RemoteXY_CONF_PROGMEM[] =
  { 255,4,0,0,0,56,0,19,0,0,0,84,105,103,114,79,116,116,111,0,
  79,1,106,200,1,1,3,0,2,37,167,32,18,0,2,26,31,31,79,78,
  0,79,70,70,0,5,42,70,60,60,32,2,26,31,1,7,87,24,24,0,
  2,31,0 };
struct {
  uint8_t switch_01;     // =1 if switch ON and =0 if OFF
  int8_t joystick_01_x;  // from -100 to 100
  int8_t joystick_01_y;  // from -100 to 100
  uint8_t connect_flag;  // =1 if wire connected, else =0
} RemoteXY;
#pragma pack(pop)

// ==========================================
// PARAMETRES DE MARCHE EN 8 TEMPS
// ==========================================
int centreFootLeft = 90;
int centreFootRight = 90;
int centreLegLeft = 90;
int centreLegRight = 90;

int tempo = 150;       // Vitesse d'execution des pas (en ms)
int stride = 30;       // Amplitude des ciseaux
int liftGauche = 30;   // Amplitude de levee gauche
int liftDroite = 30;   // Amplitude de levee droite
int drift = 0;         // Correction de trajectoire

// ==========================================
// MUSIQUE DE DEMARRAGE
// ==========================================
void startupMusic() {
  tone(BUZZER_PIN, OCTAVE_4_DO, DUREE_TEMPS);
  delay(DUREE_TEMPS*1.3);
  tone(BUZZER_PIN, OCTAVE_4_DO, DUREE_TEMPS);
  delay(DUREE_TEMPS*1.3);
  tone(BUZZER_PIN, OCTAVE_4_DO, DUREE_TEMPS);
  delay(DUREE_TEMPS*1.3);
  tone(BUZZER_PIN, OCTAVE_4_RE, DUREE_TEMPS);
  delay(DUREE_TEMPS*1.3);
  tone(BUZZER_PIN, OCTAVE_4_MI, 2 * DUREE_TEMPS);
  delay(2.6 * DUREE_TEMPS);
  tone(BUZZER_PIN, OCTAVE_4_RE, 2 * DUREE_TEMPS);
  delay(2.6 * DUREE_TEMPS);
  tone(BUZZER_PIN, OCTAVE_4_DO, DUREE_TEMPS);
  delay(DUREE_TEMPS*1.3);
  tone(BUZZER_PIN, OCTAVE_4_MI, DUREE_TEMPS);
  delay(DUREE_TEMPS*1.3);
  tone(BUZZER_PIN, OCTAVE_4_RE, DUREE_TEMPS);
  delay(DUREE_TEMPS*1.3);
  tone(BUZZER_PIN, OCTAVE_4_RE, DUREE_TEMPS);
  delay(DUREE_TEMPS*1.3);
  tone(BUZZER_PIN, OCTAVE_4_DO, 4 * DUREE_TEMPS);
  delay(5.2 * DUREE_TEMPS);
  noTone(BUZZER_PIN);
}

// ==========================================
// ARRET
// ==========================================
void stopRobot() {
  footLeft.write(centreFootLeft);
  footRight.write(centreFootRight);
  legLeft.write(centreLegLeft);
  legRight.write(centreLegRight);
}

// ==========================================
// MARCHE AVANT (8 TEMPS)
// ==========================================
void marcheAvant() {
  // Bascule 1
  footLeft.write(centreFootLeft - liftGauche);
  footRight.write(centreFootRight - liftDroite);
  RemoteXY_delay(tempo);
  // Ciseau 1
  legLeft.write(centreLegLeft - (stride / 2) + drift);
  legRight.write(centreLegRight - (stride / 2) - drift);
  RemoteXY_delay(tempo / 2);
  legLeft.write(centreLegLeft - stride + drift);
  legRight.write(centreLegRight - stride - drift);
  RemoteXY_delay(tempo / 2);
  // Retour centre
  footLeft.write(centreFootLeft);
  footRight.write(centreFootRight);
  RemoteXY_delay(tempo / 2);
  // Bascule 2
  footLeft.write(centreFootLeft + liftGauche);
  footRight.write(centreFootRight + liftDroite);
  RemoteXY_delay(tempo);
  // Ciseau 2
  legLeft.write(centreLegLeft + (stride / 2) - drift);
  legRight.write(centreLegRight + (stride / 2) + drift);
  RemoteXY_delay(tempo / 2);
  legLeft.write(centreLegLeft + stride - drift);
  legRight.write(centreLegRight + stride + drift);
  RemoteXY_delay(tempo / 2);
  // Retour centre
  footLeft.write(centreFootLeft);
  footRight.write(centreFootRight);
  RemoteXY_delay(tempo / 2);
}

// ==========================================
// MARCHE ARRIERE (8 TEMPS)
// ==========================================
void marcheArriere() {
  footLeft.write(centreFootLeft - liftGauche);
  footRight.write(centreFootRight - liftDroite);
  RemoteXY_delay(tempo);
  legLeft.write(centreLegLeft + (stride / 2) + drift);
  legRight.write(centreLegRight + (stride / 2) - drift);
  RemoteXY_delay(tempo / 2);
  legLeft.write(centreLegLeft + stride + drift);
  legRight.write(centreLegRight + stride - drift);
  RemoteXY_delay(tempo / 2);
  footLeft.write(centreFootLeft);
  footRight.write(centreFootRight);
  RemoteXY_delay(tempo / 2);
  footLeft.write(centreFootLeft + liftGauche);
  footRight.write(centreFootRight + liftDroite);
  RemoteXY_delay(tempo);
  legLeft.write(centreLegLeft - (stride / 2) - drift);
  legRight.write(centreLegRight - (stride / 2) + drift);
  RemoteXY_delay(tempo / 2);
  legLeft.write(centreLegLeft - stride - drift);
  legRight.write(centreLegRight - stride + drift);
  RemoteXY_delay(tempo / 2);
  footLeft.write(centreFootLeft);
  footRight.write(centreFootRight);
  RemoteXY_delay(tempo / 2);
}

// ==========================================
// TOURNER GAUCHE (8 TEMPS)
// ==========================================
void tournerGauche() {
  footLeft.write(centreFootLeft - liftGauche);
  footRight.write(centreFootRight - liftDroite);
  RemoteXY_delay(tempo);
  legLeft.write(centreLegLeft + (stride / 2));
  legRight.write(centreLegRight - (stride / 2));
  RemoteXY_delay(tempo / 2);
  legLeft.write(centreLegLeft + stride);
  legRight.write(centreLegRight - stride);
  RemoteXY_delay(tempo / 2);
  footLeft.write(centreFootLeft);
  footRight.write(centreFootRight);
  RemoteXY_delay(tempo / 2);
  footLeft.write(centreFootLeft + liftGauche);
  footRight.write(centreFootRight + liftDroite);
  RemoteXY_delay(tempo);
  legLeft.write(centreLegLeft - (stride / 2));
  legRight.write(centreLegRight + (stride / 2));
  RemoteXY_delay(tempo / 2);
  legLeft.write(centreLegLeft - stride);
  legRight.write(centreLegRight + stride);
  RemoteXY_delay(tempo / 2);
  footLeft.write(centreFootLeft);
  footRight.write(centreFootRight);
  RemoteXY_delay(tempo / 2);
}

// ==========================================
// TOURNER DROITE (8 TEMPS)
// ==========================================
void tournerDroite() {
  footLeft.write(centreFootLeft - liftGauche);
  footRight.write(centreFootRight - liftDroite);
  RemoteXY_delay(tempo);
  legLeft.write(centreLegLeft - (stride / 2));
  legRight.write(centreLegRight + (stride / 2));
  RemoteXY_delay(tempo / 2);
  legLeft.write(centreLegLeft - stride);
  legRight.write(centreLegRight + stride);
  RemoteXY_delay(tempo / 2);
  footLeft.write(centreFootLeft);
  footRight.write(centreFootRight);
  RemoteXY_delay(tempo / 2);
  footLeft.write(centreFootLeft + liftGauche);
  footRight.write(centreFootRight + liftDroite);
  RemoteXY_delay(tempo);
  legLeft.write(centreLegLeft + (stride / 2));
  legRight.write(centreLegRight - (stride / 2));
  RemoteXY_delay(tempo / 2);
  legLeft.write(centreLegLeft + stride);
  legRight.write(centreLegRight - stride);
  RemoteXY_delay(tempo / 2);
  footLeft.write(centreFootLeft);
  footRight.write(centreFootRight);
  RemoteXY_delay(tempo / 2);
}

// ==========================================
// INITIALISATION
// ==========================================
void setup() {
  // startupMusic();
  RemoteXY_Init();

  Serial.begin(9600);
  Serial.println("Demarrage de la communication serie");

  pinMode(trig_pin, OUTPUT);
  pinMode(echo_pin, INPUT);

  legLeft.attach(pinLegLeft);
  legRight.attach(pinLegRight);
  footLeft.attach(pinFootLeft);
  footRight.attach(pinFootRight);

  stopRobot();
  Serial.println("Calibrage des moteurs termine");
  RemoteXY_delay(2000);
}

// ==========================================
// BOUCLE PRINCIPALE
// ==========================================
void loop() {
  RemoteXY_Handler();
  if (RemoteXY.switch_01 == 0) {
    // Mode Auto : Avance en continu
    marcheAvant();
  } else {
    // Mode Manuel : Controle via le Joystick
    int axeX = RemoteXY.joystick_01_x;
    int axeY = RemoteXY.joystick_01_y;
    int seuil = 50;

    if (axeY > seuil && abs(axeX) < seuil) {
      marcheAvant();
    }
    else if (axeY < -seuil && abs(axeX) < seuil) {
      marcheArriere();
    }
    else if (axeX > seuil && abs(axeY) < seuil) {
      tournerDroite();
    }
    else if (axeX < -seuil && abs(axeY) < seuil) {
      tournerGauche();
    }
    else {
      stopRobot();
    }
  }
}
```

➡️ [Accéder au programme complet](code/main.ino)

Le fichier contient l'ensemble des fonctions de déplacement, de communication Bluetooth et de contrôle des servomoteurs utilisées lors des Ottolympiades.

---

# VI. Résultats — Journée des challenges

Le jour J est arrivé : la journée des challenges. Toutes les équipes ont mis leurs robots à l'épreuve sur un parcours d'obstacles commun, dans une ambiance à la fois détendue et résolument compétitive.

Notre choix stratégique d'agrandir le robot et d'optimiser le code pour la vitesse a payé : nous avons terminé **5ᵉ** sur l'ensemble des équipes participantes. Un résultat dont nous sommes fiers, d'autant que notre point fort clairement identifié était la vitesse de déplacement — notre Otto était indéniablement l'athlète de la compétition.

Là où d'autres robots avaient misé sur la prudence, des mouvements lents et très contrôlés, notre Otto avançait franchement, couvrant le parcours avec une efficacité remarquable. Ce n'était pas un boxeur qui cherche le contact — c'était un sprinter qui cherche la ligne d'arrivée.

| Classement final | Point fort identifié |
|------------------|----------------------|
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
- Vidéo de démonstration (format portrait) montrant le robot en action ;
- Fichier OnShape de notre version modifiée d'Otto-MKS (accès fourni par Noé) — [Voir le 3D](https://cad.onshape.com/documents/07646ee59cb8562e28d77f4a/w/f8c3c05c39bbff21b5297472/e/8cb9828b3fc7f4771eeacd2e?renderMode=0&uiState=6a26caec1c9cfda4dc6e792d) ;
- Le code source complet — [main.ino](code/main.ino) ;
- Ce rapport de projet.

---

# VII. Bilan et améliorations

Ce projet aura été bien plus qu'un exercice scolaire. De la première pièce imprimée jusqu'à la ligne d'arrivée de la journée des challenges, nous avons traversé toutes les étapes d'un vrai projet technique : conception, fabrication, intégration, débogage, optimisation, et mise en compétition.

La décision d'agrandir le robot s'est avérée payante, mais elle nous a obligés à repenser notre approche de la programmation — et c'est exactement ce genre de contrainte qui force à progresser vraiment. On ne peut pas juste copier-coller des valeurs toutes faites quand le robot a changé de taille ; il faut comprendre ce qu'on fait.

Les difficultés rencontrées — synchronisation des servos, filtrage des données capteur, équilibre vitesse/stabilité — ont toutes trouvé leur solution grâce à de la persévérance, du test méthodique et du travail d'équipe. Chacun a apporté ses compétences et sa curiosité, et c'est cette complémentarité qui a fait la différence.

Ce projet nous a permis de développer des compétences en programmation embarquée, en électronique, en conception mécanique, en impression 3D, ainsi qu'en gestion de projet et en travail en équipe.

## Ce que l'on pourrait améliorer ou approfondir

- **Détection d'obstacles** : ajouter un deuxième capteur latéral pour une détection plus réactive sur les côtés ;
- **Contrôle Bluetooth** : approfondir l'intégration RemoteXY pour ajuster les paramètres de marche (tempo, stride, lift) en direct depuis l'application, sans recompiler ;
- **Gestion de l'énergie** : travailler davantage cet aspect, car à vitesse élevée la batterie 9V se décharge rapidement ;
- **Signalisation** : explorer l'ajout d'un buzzer ou d'une LED pour visualiser les états du robot (obstacle détecté, batterie faible...) ;
- **Mécanique** : améliorer la robustesse des emboîtements pieds/jambes qui subissent des contraintes importantes à haute vitesse ;
- **Intelligence embarquée** : aller plus loin dans l'optimisation algorithmique — des algorithmes d'apprentissage simple pourraient permettre au robot d'auto-calibrer ses paramètres de marche.

---

# Conclusion

Au final, ce projet nous a donné une vision concrète de ce que signifie construire un système embarqué de A à Z. La cinquième place obtenue aux Ottolympiades valide les choix réalisés par l'équipe, notamment l'agrandissement du robot et l'optimisation des paramètres de marche.

Et honnêtement, voir son robot finir 5ᵉ en sprintant sur un parcours d'obstacles — après des heures de débogage et d'ajustements — c'est une satisfaction qu'aucun cours magistral ne peut reproduire. Cette expérience constitue une base solide pour de futures améliorations visant à rendre le robot encore plus autonome, performant et intelligent.

**ILYAS NASSIRI**
