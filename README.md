[README (1).md](https://github.com/user-attachments/files/35334530/README.1.md)
# Carnet Cross-Training EPS

Carnet d'entraînement et d'évaluation **numérique** pour un cycle de cross-training en EPS. L'application tient dans **un seul fichier HTML autonome** (≈ 3,8 Mo). Le HTML, le CSS, le JavaScript et les 105 images d'exercices y sont embarqués. Il n'y a ni installation, ni dépendance, ni étape de build.

L'élève saisit son identité, suit les 7 séances du cycle, consulte une banque d'exercices illustrée, lance des chronomètres intégrés et s'auto-évalue séance par séance. Ses données sont enregistrées sur l'appareil, et une synchronisation en ligne est possible en option.

---

## Sommaire

- [Démarrage rapide](#démarrage-rapide)
- [Fonctionnalités](#fonctionnalités)
- [Contenu pédagogique](#contenu-pédagogique)
- [Architecture technique](#architecture-technique)
- [Sauvegarde des données](#sauvegarde-des-données)
- [Synchronisation cloud (optionnelle)](#synchronisation-cloud-optionnelle)
- [Personnalisation](#personnalisation)
- [Compatibilité et limites](#compatibilité-et-limites)

---

## Démarrage rapide

1. Ouvrir `Carnet-cross-training.html` dans un navigateur récent (Chrome, Edge, Firefox ou Safari, sur ordinateur, tablette ou smartphone).
2. Remplir le formulaire d'accueil : **nom**, **prénom**, **classe**, **binôme observateur** (le même pour tout le cycle).
3. Cliquer sur **« Ouvrir le carnet d'évaluation »**.
4. Choisir une séance avec les onglets *Séance 1 → Séance 7*, puis compléter les tableaux.
5. Cliquer sur **« Enregistrer cette séance »**.

> Le fichier peut être déposé sur un ENT, un Drive ou une clé USB, ou envoyé par mail. Il fonctionne aussi hors connexion. Seule l'image d'en-tête de la page d'accueil, hébergée sur Unsplash, a besoin d'Internet.

---

## Fonctionnalités

| Fonction | Description |
|---|---|
| **Page d'accueil** | Formulaire d'identité, plus deux référentiels du cycle : *Thèmes d'entraînement* et *Méthodes*. |
| **7 séances navigables** | Barre d'onglets entre les séances. Chaque séance suit la même structure en 4 parties. |
| **Banque d'exercices** | Panneau latéral fixe avec 4 onglets (Cardio, Résistance, Explosivité, Résistance + Explosivité) et 47 ateliers illustrés sur 3 niveaux. |
| **Chronomètres intégrés** | Fenêtre flottante en bas à droite, avec démarrer/pause, réinitialiser et bip sonore. Modes : Tabata 2×4′ (20″/10″), comptes à rebours de 8′, 12′, 24′, 30′ et 36′. |
| **Choix de niveau** | Pour chaque exercice : sélection du niveau, miniature et critères de réussite. |
| **Auto-évaluation** | Deux modes selon la séance (voir ci-dessous). |
| **Tableaux éditables** | Cellules `contenteditable` pour créer sa mobilité, ses étirements et son warm-up (séances 2 à 7). |
| **Choix du METCON** | Séances 4 à 7 : l'élève choisit sa piste (Circuit / AMRAP / EMOM). |
| **Construction d'entraînement** | Séances 6 et 7 : l'élève compose lui-même ses ateliers (3 ou 4 selon la méthode). |
| **Sauvegarde automatique** | `localStorage`, avec migration automatique des anciennes versions (v1 à v5). |
| **Réinitialisation** | Bouton « Réinitialiser », avec confirmation, qui efface toutes les données locales. |
| **Responsive** | Mise en page en 2 colonnes sur grand écran, 1 colonne sous 1000 px, tableaux défilables sur mobile. |

### Modes d'évaluation

- **`rating`** (séances 1 et 2) : appréciation **TOP / SO-SO / NO** par série ou par tour, saisie des répétitions (séance 1), puis **grille de ressenti** sur 5 niveaux (général, respiratoire, musculaire, psychologique, chaleur).
- **`scr`** (séances 3 à 7) : grille **Sensations · Cadence · Régulations** par palier, avec des listes déroulantes et une note libre :

| Sensations (musculaire) | Sensations (cardio) | Cadence | Régulations |
|---|---|---|---|
| RM : Relâchement musculaire | PF : Peut parler facilement | TR : Trop rapide | Augmenter rép++ / niveau++ / charge++ |
| EM : Échauffement musculaire | RA : Respiration s'accélère | S : Stable jusqu'à la fin | Augmenter rép+ / niveau+ / charge+ |
| OK : Contractions intenses | EP : Empêche de parler | OK : Diminue sur la fin | OK |
| IM : Impuissance musculaire | À bout de souffle | IF : Impossibilité de finir | Diminuer rép / niveau / charge |

---

## Contenu pédagogique

### Thèmes d'entraînement

| | Thème 1 : Tonification | Thème 2 : Renforcement | Thème 3 : Force |
|---|---|---|---|
| Profil | Le sédentaire | Le sportif curieux | Le sportif spécialiste |
| Skill | Cardio | Résistance | Explosivité |
| Warm-up | Tabata (8′) | Death by (8′ max) | For time (8′ max) |
| METCON | Circuit training (36′) | AMRAP (36′) | EMOM (36′) |
| Cadence | 1-1-1-1 | 2-2-2-2 | 3-2-max-1 |

### Structure commune d'une séance

1. **Mobilité** (5′)
2. **Warm-up** (8′)
3. **METCON** (12′ à 36′)
4. **Étirements** (5′)

### Progression du cycle

| Séance | Titre | Warm-up | METCON | Évaluation |
|---|---|---|---|---|
| 1 | Découverte tonification (cardio) | Tabata 2×4′ | Circuit training 12′ | TOP/SO-SO/NO + répétitions + ressenti |
| 2 | Découverte renforcement (résistance) | Death by 8′ | AMRAP 12′ | TOP/SO-SO/NO + ressenti |
| 3 | Découverte force (explosivité) | For time 8′ (quatuor) | EMOM 24′ | Sensations · Cadence · Régulations |
| 4 | Approfondissement de la cadence | Warm-up créé par l'élève | EMOM 36′ au choix (résistance ou explosivité) | SCR |
| 5 | Choisis ton entraînement | Warm-up créé par l'élève | Circuit / AMRAP / EMOM 36′ (ateliers proposés + 1 libre) | SCR |
| 6 | Deviens un crossfiteur | Warm-up créé par l'élève | Circuit / AMRAP / EMOM 36′ **construit par l'élève** | SCR |
| 7 | Évaluation | Warm-up créé par l'élève | Circuit / AMRAP / EMOM 36′ construit par l'élève | SCR |

On passe d'un guidage fort (séances 1 à 3 imposées) à une **autonomie croissante** (choix puis conception de l'entraînement).

---

## Architecture technique

Fichier unique, sans framework : **HTML5 + CSS + JavaScript vanilla (ES5)**, encapsulé dans une IIFE.

```
Carnet-cross-training.html
├── <head>
│   └── <style>                 Styles (layout grid, tableaux, chrono, responsive)
├── <body>
│   ├── #page-1                 Accueil : formulaire identité + référentiels
│   ├── #session-page           Page séance (titre, onglets, contenu, boutons)
│   └── #bank-aside             Banque d'exercices (panneau latéral)
└── <script>
    ├── CLOUD_SYNC              Synchronisation distante optionnelle
    ├── ASSETS_B64              105 images encodées en base64 (≈ 3,8 Mo)
    ├── Hook HTMLImageElement   Redirige "assets/from-word/xxx" vers la data URI
    ├── *_ROWS                  Découpages temporels (EMOM, Circuit, AMRAP)
    ├── SESSION_REGISTRY        Définition déclarative des 7 séances
    ├── bankExercises           47 ateliers de la banque
    ├── Données / stockage      loadData, saveData, migratePayload…
    ├── Rendu                   renderSessionPage, renderSessionTable,
    │                           renderBuilderMetconTable, renderFeelingsGrid,
    │                           renderExerciseBank…
    └── Chronomètres            startCountdown, startTabata2x4, tick, beep
```

### Points notables

- **Images embarquées** : le code référence les images par un chemin logique (`assets/from-word/image8.jpeg`). Un surcharge du setter `HTMLImageElement.prototype.src` remplace ce chemin par la data URI correspondante dans `ASSETS_B64`. Si le nom ne s'y trouve pas, le chemin d'origine est utilisé : on peut donc aussi servir de vraies images depuis un dossier `assets/from-word/`.
- **Séances déclaratives** : chaque entrée de `SESSION_REGISTRY` décrit le titre, le HTML d'échauffement et de retour au calme, le mode d'évaluation, les lignes temporelles, les exercices avec leurs niveaux, miniatures et critères, et éventuellement des pistes (`emomTracks`) ou un mode construction (`builderMode`).
- **Chronomètre** : son DOM est créé à la demande. Il se déclenche par délégation d'événement sur les boutons `.timer-btn[data-timer]`. Le bip est produit par l'API Web Audio (aucun fichier son).

---

## Sauvegarde des données

| Clé `localStorage` | Contenu |
|---|---|
| `eps_cross_training_carnet_doc_v6` | Données actuelles : identité, séances, horodatage |
| `eps_cross_training_carnet_doc_v1` … `v5` | Anciennes versions, lues puis migrées automatiquement |
| `eps_cross_training_cloud_student_id` | Identifiant anonyme (`stu_<uuid>`) pour la synchro cloud |

Format simplifié :

```json
{
  "identity": { "lastName": "", "firstName": "", "className": "", "cycleObserver": "" },
  "sessions": {
    "1": { "levels": {}, "ratings": [], "feelings": {}, "...": "..." },
    "7": { "...": "..." }
  },
  "updatedAt": 1732450000000
}
```

> ⚠️ Les données restent **dans le navigateur et sur l'appareil** où le carnet a été rempli. Si l'élève change d'appareil ou de navigateur, ou s'il vide ses données de navigation, son carnet est perdu, sauf si la synchronisation cloud est activée.

---

## Synchronisation cloud (optionnelle)

Elle est désactivée tant qu'aucune URL d'API n'est fournie. Il y a trois façons d'en définir une, par ordre de priorité :

1. Un paramètre d'URL : `Carnet-cross-training.html?api=https://mon-serveur.fr`
2. Une variable globale définie avant le script : `window.CLOUD_SYNC_API_URL = "https://mon-serveur.fr"`
3. Automatiquement, si la page est servie en HTTP sur le port **8787** (l'origine courante est alors utilisée).

### Contrat d'API attendu

| Méthode | Route | Corps / réponse |
|---|---|---|
| `GET` | `/api/carnets/:studentId` | `200` avec le JSON du carnet, ou `404` s'il n'existe pas |
| `PUT` | `/api/carnets/:studentId` | Corps JSON `{ identity, sessions, updatedAt }` |

- Envoi **décalé de 1,2 s** après chaque modification.
- Au démarrage, la version distante remplace la version locale si son `updatedAt` est plus récent.
- En cas d'erreur réseau, la sauvegarde locale est conservée et un message s'affiche.

> Le serveur n'est pas fourni avec ce fichier. Côté RGPD, les données envoyées contiennent le nom et la classe de l'élève : il faut utiliser un hébergement conforme aux règles de l'établissement.

---

## Personnalisation

| Objectif | Où modifier |
|---|---|
| Modifier une séance (exercices, niveaux, critères) | `SESSION_REGISTRY["n"]` |
| Ajouter une séance | Nouvelle entrée dans `SESSION_REGISTRY` + ajout de l'id dans `SESSION_IDS` |
| Changer les durées / paliers | Tableaux `EMOM_*_ROWS`, `CIRCUIT_*_ROWS`, `AMRAP_*_ROWS` |
| Modifier la banque d'exercices | Tableau `bankExercises` |
| Modifier les grilles d'auto-évaluation | `SCR_*_CHOICES` et `SCR_LEGEND_ROWS*` |
| Ajouter un chrono | Bouton `data-timer="countdown-XX"` + cas correspondant dans l'écouteur de clic final |
| Remplacer une image | Clé correspondante dans `ASSETS_B64` (base64), ou fichier dans `assets/from-word/` |
| Couleurs / mise en page | Bloc `<style>` |

> 💡 Si le format des données change, incrémentez `STORAGE_KEY` (par exemple `…_v7`) et complétez `migratePayload()` pour garder les carnets existants.

> 💡 La ligne `ASSETS_B64` fait plus de 3 millions de caractères. Utilisez un éditeur capable de gérer les très longues lignes (VS Code, Sublime Text), ou repliez cette ligne.

---

## Compatibilité et limites

- Navigateurs récents (ES5, `localStorage`, `fetch`, Web Audio API).
- Aucune feuille de style d'impression dédiée : l'impression directe du carnet n'est pas optimisée.
- Pas d'export des résultats (CSV/PDF) : les données restent dans le navigateur ou sur le serveur de synchronisation.
- Pas de vue enseignant pour regrouper les carnets d'une classe : il faut passer par l'API cloud.
- L'image d'en-tête (Unsplash) ne s'affiche pas hors connexion.

---

*Carnet conçu pour un cycle de cross-training en EPS (collège / lycée).*
