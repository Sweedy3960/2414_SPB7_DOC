# 2414_SPB7 – Testeur de Sprinkler

Ce projet implémente un système embarqué pour le test et la gestion de modules Sprinkler, basé sur une architecture modulaire et des tâches gérées par machine à états (FSM), pour microcontrôleur PIC32.

## Sommaire

- [Présentation](#présentation)
- [Fonctionnalités principales](#fonctionnalités-principales)
- [Organisation du projet](#organisation-du-projet)
- [Tableau des fichiers principaux](#tableau-des-fichiers-principaux)
- [Environnement de développement](#environnement-de-développement)
- [Compilation](#compilation)
- [Utilisation](#utilisation)
- [Suivi des tâches](#suivi-des-tâches)
- [Documentation](#documentation)
- [Ressources](#ressources)
- [Notes](#notes)

## Présentation

Ce dépôt contient le code source, la documentation et la configuration pour le projet de testeur de modules Sprinkler.  
L’architecture est orientée événements et intègre la gestion de multiples périphériques (RTC, Touch, ADC, Display, LED, Relais, Buzzer, Bluetooth, SD Card).

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
- **Compilateur** : XC32 v2.5 
- **Plateforme cible** : Microcontrôleur PIC32mx79512fl

## Compilation

1. Cloner le repos en local sur la machine 
2. Décompresser le dossier projet dans " C:\microchip\harmony\v2_06\apps\MINF" 
3. Dans Mplab ouvrir le prrojet souhaiter 
4. Vérifier la configuration du compilateur (XC32).
5. Compiler le projet (`Build Project`).
6. Programmer la cible via l’outil de programmation (PICkit, ICD, etc.).

## Utilisation

- Actuellement en développement pas d'utilisation  "normale", le projet flasher est le "SPSPB7_Assembly" 
- Pour l'instant alimenter le prjet en +3V3 sur les fils qui ressortes du boitier 
- une séquence de bienvenus s'affiche, les actions sur les toucbes capacitives on un effet sur les leds et écrans 

- Le  projet "2414-DES_SP7_TestSprinkler" est l'ancienne version du programme de test, il n'est pas utilisable simplement
- il faut l'utiliser en débug et "activer" les fonctionalité à testet grace à des variables globales
- sur cette ancienne version, les fonctionnalité ont été validée jsuqu'a la carte SD 

L'ordre des fonctionalité implémentée: 
- voir rapport

## Taches à venir

- [ ] Repartir sur un projet MPlab vierge et faire la configuration corectement
- [ ] Finir inpmlémenter appInputs -> refractor sm et reconfigurer ADC pour lecture plus rapide 
- [ ] Ajouter la gestion de la tache et crée les fonction de handling
- [ ] Crée la logique pour reporter les entrée sur les sorties 
- [ ] Ajouter l'app MCP /RTC 
- [ ] Ajouter l'app Bluetooth
- [ ] Ajouter l'app Buzzer

## Documentation

La documentation technique (Doxygen, schémas, diagrammes) est disponible dans le dossier du projet:

2414-DES_SP7_TestSprinkler doc : C:\microchip\harmony\v2_06\apps\MINF\Projet\2414-DES_SP7_TestSprinkler\firmware\src\html\index.html"
SPSPB7_Assembly doc: "C:\microchip\harmony\v2_06\apps\MINF\Projet\SPB7_Assembly\firmware\src\html\index.html"

## Ressources

- [MPLAB X IDE](https://www.microchip.com/en-us/tools-resources/develop/mplab-x-ide)
- [Doxygen](https://www.doxygen.nl/index.html)
- [Documentation Microchip PIC32MM](https://www.microchip.com/wwwproducts/en/PIC32MM0064GPL020)
- [VS Code](https://code.visualstudio.com/)
- [Graphviz](https://graphviz.gitlab.io/)

## Notes

- Pour toute modification, mettre à jour ce README et la checklist.
- Les chemins et fichiers peuvent évoluer selon l’avancement du projet.
