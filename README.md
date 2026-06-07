# LabSec8 – Analyse Statique Android



---

## Contexte

Ce laboratoire présente une démarche d'analyse statique appliquée à une application Android pédagogique issue du projet OWASP MSTG.

L'objectif est de mettre en place un processus d'analyse reproductible permettant :

* d'identifier précisément l'artefact étudié ;
* de documenter le périmètre de l'analyse ;
* d'utiliser plusieurs outils d'analyse statique ;
* de centraliser les résultats obtenus ;
* de préparer un triage des constats selon les bonnes pratiques de sécurité mobile.

L'analyse a été réalisée dans un environnement de laboratoire contrôlé et autorisé.

---

## Objectifs du Laboratoire

* Définir le périmètre d'analyse.
* Assurer la traçabilité de l'artefact étudié.
* Calculer et documenter l'empreinte SHA-256 de l'APK.
* Réaliser une première analyse avec BeVigil.
* Effectuer une analyse complémentaire avec Yaazhini.
* Consolider les résultats dans un processus de triage.
* Préparer l'association des constats avec les référentiels OWASP MASVS.

---

## Informations sur la Cible

| Élément       | Valeur                                                             |
| ------------- | ------------------------------------------------------------------ |
| Application   | `UnCrackable-Level1.apk`                                           |
| Type          | APK Android                                                        |
| Hash SHA-256  | `1DA8BF57D266109F9A07C01BF7111A1975CE01F190B9D914BCD3AE3DBEF96F21` |
| Source        | Support de cours                                                   |
| Environnement | Windows 11 Pro                                                     |

---

## Organisation du Workspace

Afin de garantir la reproductibilité de l'analyse, le projet est structuré en plusieurs dossiers dédiés.

```text
LabSec8/
│
├── 00-scope/
├── 01-bevigil/
├── 02-yaazhini/
├── 03-triage/
└── 04-report/
```

### Structure du Workspace

![Structure Workspace](<screens/Capture d'écran 2026-06-01 093533.png>)

Chaque dossier correspond à une étape spécifique du processus d'analyse.

---

## Définition du Périmètre

Le dossier `00-scope` contient les éléments permettant de définir le cadre du laboratoire.

Les informations documentées incluent :

* la cible autorisée ;
* le contexte pédagogique ;
* les limites du laboratoire ;
* les règles de manipulation de l'APK.

### Dossier de Scope

![Dossier Scope](<screens/Capture d'écran 2026-06-01 093752.png>)

Cette étape permet de garantir que l'analyse reste conforme au périmètre défini.

---

## Préparation de l'Analyse

Des fichiers de suivi sont créés afin de conserver les informations importantes du laboratoire.

### Fichiers de Traçabilité

* `analyse_info.txt`
* `commands.log`

Ces fichiers enregistrent :

* l'identité de l'analyste ;
* la date d'analyse ;
* l'environnement utilisé ;
* les commandes exécutées ;
* les informations relatives à l'APK.

### Préparation du Workspace

![Préparation](<screens/Capture d'écran 2026-06-01 093606.png>)

---

## Identification de l'Artefact

L'APK est copiée dans le périmètre d'analyse puis identifiée à l'aide d'une empreinte cryptographique.

### Informations d'Analyse

![Informations Analyse](<screens/Capture d'écran 2026-06-01 093711.png>)

### Calcul du Hash SHA-256

![Hash APK](<screens/Capture d'écran 2026-06-01 093738.png>)

Le hash SHA-256 permet :

* d'identifier de manière unique l'APK analysée ;
* de garantir l'intégrité du fichier ;
* d'assurer la reproductibilité des résultats.

---

## Analyse avec BeVigil

Une première analyse est réalisée à l'aide de BeVigil.

L'objectif est d'obtenir rapidement des informations de sécurité concernant l'application et d'identifier d'éventuels indicateurs intéressants pour la suite de l'analyse.

### Résultats BeVigil

![Résultat BeVigil](<screens/Capture d'écran 2026-06-01 095300.png>)

Les résultats sont conservés comme pistes d'investigation et de validation.

---

## Analyse avec Yaazhini

Une seconde analyse est effectuée avec Yaazhini afin d'obtenir une vue plus détaillée du contenu de l'application.

L'outil permet notamment de :

* parcourir les composants Android ;
* examiner les permissions ;
* identifier certaines catégories de risques ;
* produire une synthèse exploitable pour le triage.

### Tableau de Résultats

![Yaazhini Tableau](<screens/Capture d'écran 2026-06-01 095324.png>)

Les résultats sont présentés sous forme de tableau facilitant leur lecture.

### Synthèse de l'Analyse

![Yaazhini Synthèse](<screens/Capture d'écran 2026-06-01 095334.png>)

Cette synthèse sert de base aux étapes suivantes de validation et de classification.

---

## Triage des Résultats

Les constats issus de BeVigil et Yaazhini sont regroupés dans le dossier :

```text
03-triage
```

Les objectifs du triage sont :

* éliminer les doublons ;
* regrouper les observations similaires ;
* identifier les résultats pertinents ;
* préparer le rapprochement avec les contrôles OWASP MASVS.

Cette phase améliore la qualité et la cohérence du rapport final.

---

## Références OWASP

Lorsque cela est pertinent, les constats peuvent être rapprochés des exigences définies dans :

* OWASP MASVS (Mobile Application Security Verification Standard)
* OWASP MSTG (Mobile Security Testing Guide)

Cette correspondance facilite l'évaluation du niveau de sécurité de l'application analysée.

---

## Résultats

Le laboratoire a permis de produire :

* ✅ Un périmètre d'analyse documenté.
* ✅ Une identification complète de l'artefact via SHA-256.
* ✅ Un workspace structuré et reproductible.
* ✅ Une analyse préliminaire avec BeVigil.
* ✅ Une analyse détaillée avec Yaazhini.
* ✅ Une consolidation des constats dans un processus de triage.
* ✅ Une base exploitable pour le rapprochement avec OWASP MASVS.

---

## Conclusion

Ce laboratoire a permis de mettre en œuvre une méthodologie d'analyse statique Android structurée autour de la traçabilité, de l'identification des artefacts et de l'utilisation d'outils spécialisés.

L'approche adoptée facilite la reproductibilité des analyses et prépare efficacement les étapes ultérieures d'évaluation de sécurité mobile, de triage des vulnérabilités et de cartographie vers les référentiels OWASP.
