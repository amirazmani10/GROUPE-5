title: Documentation Otto-MKS
layout: home
🤖 Robot Otto-MKS — I1 Groupe 5

Robot humanoïde bipède autonome — UniLaSalle Amiens, École d'ingénieurs Énergie & Numérique. Année 2025-2026.

Équipe : Ilyas Nassiri · Amir Azmani · Noé Obame
Résultat : 🏅 5ᵉ place aux Ottolympiades — point fort : la vitesse de déplacement.

Introduction
Dans le cadre de ce projet, notre équipe a relevé le défi de concevoir et de faire fonctionner un robot humanoïde bipède : Otto-MKS. L'objectif n'était pas seulement d'assembler des pièces et d'écrire quelques lignes de code, mais de créer un robot capable d'évoluer en autonomie dans un parcours semé d'obstacles.
Le projet nous a plongés dans plusieurs disciplines en même temps : programmation embarquée, électronique, mécanique, et un peu de design via l'impression 3D. Apprendre à faire dialoguer tous ces éléments ensemble — sans que tout s'effondre lors de la compétition — c'était toute la difficulté, et toute la richesse de cette expérience.

I. Présentation du projet
Contexte
Le projet Otto-MKS s'inscrit dans les activités du MakerSpace de l'école, un espace dédié à la fabrication numérique et au prototypage. Otto est un robot open-source, abordable, personnalisable et éducatif, bâti autour d'un microcontrôleur ESP32-C3 compatible Arduino. Notre démarche : nous approprier la base pour la pousser plus loin — plus grand, plus rapide, plus performant.
Objectifs

Concevoir et assembler un robot bipède fonctionnel
Programmer des déplacements autonomes fluides et stables
Intégrer un capteur de détection d'obstacles
Optimiser les performances pour la journée des challenges
Maîtriser l'environnement Arduino IDE et le langage C/C++
Exploiter l'impression 3D pour personnaliser la structure


II. Matériel et composants
ComposantQuantitéFonctionCarte électronique OTTO-MKS1Contrôle du robot (ESP32-C3)Servomoteurs 9g4Actionneurs — mouvements des jambes et piedsCapteur HC-SR041Détection d'obstacles par ultrasonsBatterie 9V1Alimentation autonome du robotCâble USB-C1Programmation et test via Arduino IDE

La carte Otto-MKS est le cerveau du robot : un ESP32-C3 qui gère l'alimentation, les servomoteurs, les capteurs et la communication Wi-Fi/Bluetooth.
Les 4 servomoteurs 9g donnent vie au robot : chacun se positionne sur un angle précis pour les mouvements des hanches et des pieds.
Le capteur HC-SR04 est les « yeux » du robot : il mesure la distance d'un obstacle par ultrasons.
La batterie 9V assure l'autonomie ; le câble USB-C sert au téléversement du code et au monitoring en temps réel.


III. Conception et assemblage
Impression 3D
La première étape a été l'impression 3D des pièces (tête, tronc, jambes, pieds) sur l'imprimante du MakerSpace. Notre première décision marquante : agrandir le robot — des enjambées plus larges, donc plus de vitesse à fréquence de pas égale. Chaque pièce a été inspectée et ébavurée pour s'assembler sans forcer.
Assemblage mécanique
Montage du châssis, puis installation des servomoteurs dans leurs logements (hanches et jambes). Un positionnement précis est crucial : le moindre jeu mécanique se traduit par une instabilité à la marche. Jambes et pieds ont ensuite été emboîtés sur les axes, avec vérification de l'alignement à chaque étape.
Câblage électronique
Chaque composant a été raccordé à la carte selon son affectation (servos, HC-SR04, alimentation). Polarités et solidité des connexions ont été vérifiées avant la mise sous tension — une mauvaise connexion peut rester silencieuse puis provoquer un bug au pire moment.

IV. Programmation
Environnement
Développement sous Arduino IDE, en C/C++, compilation locale puis téléversement sur l'ESP32-C3 via USB-C.
Adapter le code à la version agrandie
Agrandir le robot physiquement ne suffit pas : avec des jambes plus longues, les mêmes angles de servos produisent des mouvements différents. Nous avons retravaillé en profondeur les paramètres de marche (amplitudes, vitesses, délais) pour maximiser la vitesse tout en gardant le robot stable — un robot qui tombe est disqualifié.
Fonctions programmées

Marche avant / arrière : séquence coordonnée en 8 temps des 4 servomoteurs
Rotation gauche / droite : virages contrôlés pour le slalom
Mouvements de hanches : ajustés pour une démarche stable
Télécommande Bluetooth : via RemoteXY (joystick + switch auto/manuel)
Détection d'obstacles : HC-SR04 câblé et broches déclarées ; logique d'évitement en cours (piste d'amélioration prioritaire)

Les galères de code — et comment on s'en est sortis
La synchronisation des servomoteurs était le principal casse-tête : des timings mal calibrés provoquaient des oscillations, voire des chutes. Autre point délicat : le HC-SR04 renvoyait parfois des valeurs aberrantes — nous avons ajouté des filtres logiques pour ignorer les mesures incohérentes. Frustrant sur le moment, mais c'est ce débogage itératif qui forge de vraies compétences d'ingénieur.

V. Résultats — Journée des challenges
Notre choix d'agrandir le robot et d'optimiser le code pour la vitesse a payé : 5ᵉ place sur l'ensemble des équipes. Là où d'autres misaient sur des mouvements lents et prudents, notre Otto avançait franchement. Ce n'était pas un boxeur qui cherche le contact — c'était un sprinter qui cherche la ligne d'arrivée.
Classement finalPoint fort identifié5ᵉ placeVitesse de déplacement
Livrables : robot fonctionnel présenté aux Ottolympiades · vidéo de démonstration · fichier OnShape de notre version modifiée (accès fourni par Noé) · ce rapport.

VI. Bilan et améliorations
Ce projet a été bien plus qu'un exercice scolaire : conception, fabrication, intégration, débogage, optimisation et compétition. Agrandir le robot nous a obligés à comprendre ce que nous faisions plutôt que de copier des valeurs toutes faites.
Pistes d'amélioration :

Ajouter un deuxième capteur latéral pour une détection plus réactive sur les côtés
Approfondir l'intégration Bluetooth : ajuster tempo / stride / lift en live depuis l'app, sans recompiler
Mieux gérer l'énergie : à haute vitesse, la batterie 9V se décharge vite
Ajouter buzzer / LED pour visualiser les états (obstacle, batterie faible…)
Renforcer la robustesse mécanique des emboîtements pieds/jambes
Explorer des algorithmes d'auto-calibration des paramètres de marche


VII. Code source — main.ino
Code complet téléversé sur l'ESP32-C3 : fonctions de déplacement, télécommande Bluetooth (RemoteXY) et mode autonome.
Paramètres de marche clés : tempo (vitesse des pas), stride (amplitude des ciseaux), liftGauche / liftDroite (levée), drift (correction de trajectoire).
Bibliothèques : ESP32Servo, RemoteXY, BLEDevice, notes.h.
cpp#include <Arduino.h>
#include <ESP32Servo.h>

// RemoteXY select connection mode and include library
#define REMOTEXY_MODE__ESP32CORE_BLE
#include <BLEDevice.h>

// ==========================================
// ⚙️ PARAMÈTRES BLUETOOTH
// ==========================================
#define REMOTEXY_BLUETOOTH_NAME "Otto"
// (Le mot de passe a été retiré)

#include <RemoteXY.h>

// Définition des fréquences des notes de musiques
#include "notes.h"
#define DUREE_TEMPS 300
#define BUZZER_PIN D0

// ==========================================
// ⚙️ DÉCLARATION DES MOTEURS ET CAPTEURS
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
// 📱 CONFIGURATION REMOTEXY
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
// ⚙️ PARAMÈTRES DE MARCHE EN 8 TEMPS
// ==========================================
int centreFootLeft = 90;
int centreFootRight = 90;
int centreLegLeft = 90;
int centreLegRight = 90;

int tempo = 150;       // Vitesse d'exécution des pas (en ms)
int stride = 30;       // Amplitude des ciseaux
int liftGauche = 30;   // Amplitude de levée gauche
int liftDroite = 30;   // Amplitude de levée droite
int drift = 0;         // Correction de trajectoire

// ==========================================
// 🎵 MUSIQUE DE DÉMARRAGE
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
// 🛑 ARRÊT
// ==========================================
void stopRobot() {
  footLeft.write(centreFootLeft);
  footRight.write(centreFootRight);
  legLeft.write(centreLegLeft);
  legRight.write(centreLegRight);
}

// ==========================================
// ⬆️ MARCHE AVANT (8 TEMPS)
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
// ⬇️ MARCHE ARRIÈRE (8 TEMPS)
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
// ⬅️ TOURNER GAUCHE (8 TEMPS)
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
// ➡️ TOURNER DROITE (8 TEMPS)
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
// 🚀 INITIALISATION
// ==========================================
void setup() {
  // startupMusic();
  RemoteXY_Init();

  Serial.begin(9600);
  Serial.println("Démarrage de la communication série");

  pinMode(trig_pin, OUTPUT);
  pinMode(echo_pin, INPUT);

  legLeft.attach(pinLegLeft);
  legRight.attach(pinLegRight);
  footLeft.attach(pinFootLeft);
  footRight.attach(pinFootRight);

  stopRobot();
  Serial.println("Calibrage des moteurs terminé");
  RemoteXY_delay(2000);
}

// ==========================================
// 🔄 BOUCLE PRINCIPALE
// ==========================================
void loop() {
  RemoteXY_Handler();
  if (RemoteXY.switch_01 == 0) {
    // Mode Auto : Avance en continu
    marcheAvant();
  } else {
    // Mode Manuel : Contrôle via le Joystick
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

<div align="center">
<strong>Ilyas Nassiri · Amir Azmani · Noé Obame</strong><br>
I1 Groupe 5 — UniLaSalle Amiens — 2025-2026
</div>
