# 2414_SPB7 – Testeur de Sprinkler

## Description

Ce projet vise à développer un système embarqué pour le test et la gestion de modules Sprinkler, basé sur une architecture modulaire et des tâches gérées par machine à états (FSM). Il intègre la gestion de multiples périphériques (RTC, Touch, ADC, Display, LED, Relais, Buzzer, Bluetooth, SD Card) et propose une architecture orientée événements pour la communication inter-modules.

## Fonctionnalités principales

- Portage et test de modules (RTC, Touch, ADC, Display, LED, Relais, Buzzer, BT, SD)
- Gestion des tâches via FSM (Harmony)
- Bus d’événements (publish/subscribe)
- Contrôle dynamique des modules (activation, désactivation, flags)
- Gestion des accès I2C/SPI pour éviter les conflits
- Intégration dans la boucle système `SYS_Tasks()`
- Tests de robustesse (non-blocage, endurance SD, consommation)

## Organisation du projet

```
.
├── README.MD
├── doc/
│   ├── ... (documents techniques, schémas, grilles d’évaluation, etc.)
│   ├── EstimPrice/
│   ├── garbage/
│   ├── others/
│   ├── parts/
│   ├── Project Outputs for .../
│   ├── rendus/
├── hard/
│   ├── ... (fichiers hardware, PCB, STEP, etc.)
├── mec/
│   ├── ... (fichiers mécaniques, STEP, DXF, SLDASM, etc.)
├── soft/
│   ├── Chemin.txt
│   ├── Projet.zip
├── tools/
```

## Tableau des fichiers principaux

| Chemin relatif                                              | Description                                      |
|------------------------------------------------------------|--------------------------------------------------|
| `README.MD`                                                | Présentation et suivi du projet                  |
| `doc/`                                                     | Documentation, rapports, schémas, grilles        |
| `doc/EstimPrice/`                                          | Estimations de prix, images de commandes         |
| `doc/garbage/`                                             | Archives, idées, schémas à trier                 |
| `doc/others/`                                              | Notes techniques, calculs, docs annexes          |
| `doc/parts/`                                               | Datasheets, notes d’application                  |
| `doc/Project Outputs for 2414_SAG/`                        | Sorties CAO, DRC, EuroCircuits, docs design      |
| `doc/Project Outputs for 2414_ScreenHolder/`               | Idem pour ScreenHolder                           |
| `doc/Project Outputs for 2414_TesteurDeSprinkler_SPB7/`    | Idem pour TesteurDeSprinkler_SPB7                |
| `doc/Project Outputs for 2414_TesteurDeSprinkler_TouchCapa/`| Idem pour TouchCapa                              |
| `hard/`                                                    | Fichiers hardware, PCB, empreintes, etc.         |
| `mec/`                                                     | Fichiers mécaniques, STEP, DXF, SLDASM           |
| `soft/`                                                    | Logiciel embarqué, chemins, archives projet      |
| `tools/`                                                   | Outils divers liés au projet                     |

## Environnement de développement

- **IDE recommandé** : MPLAB X IDE (Microchip) ou équivalent compatible Harmony
- **Version Harmony** : à préciser selon le portage (ex : Harmony v3)
- **Compilateur** : XC32 (Microchip) ou compatible
- **Plateforme cible** : Microcontrôleur PIC32 (à préciser selon la carte)

## Compilation

1. Ouvrir le projet dans l’IDE recommandé.
2. Vérifier la configuration du compilateur (XC32).
3. Compiler le projet (Build Project).
4. Programmer la cible via l’outil de programmation (PICkit, ICD, etc.).

## Suivi des tâches (extrait)

- [ ] Portage et test des modules (RTC, Touch, ADC, etc.)
- [ ] Intégration du bus d’événements
- [ ] Gestion dynamique des modules
- [ ] Validation non-blocante et tests d’endurance
- [ ] Optimisation mémoire et flash

## Notes

- Pour toute modification, mettre à jour ce README et la checklist.
- Les chemins et fichiers peuvent évoluer selon l’avancement du projet.