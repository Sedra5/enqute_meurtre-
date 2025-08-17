# enqute_meurtre
# Système d'Enquête Policière en Prolog

Un système expert développé en Prolog pour simuler et analyser des enquêtes criminelles. Le système utilise des faits et des règles d'inférence pour calculer des scores de suspicion et identifier des suspects potentiels.

## 🎯 Fonctionnalités Principales

- **Calcul automatique de scores de suspicion** basé sur multiple critères
- **Analyse des motifs** (héritage, dettes, rivalités professionnelles, etc.)
- **Vérification des alibis** et détection des incohérences
- **Évaluation des preuves physiques** avec niveaux de fiabilité
- **Analyse des témoignages** et comportements suspects
- **Génération de rapports** d'enquête complets
- **Recommandations d'action** pour les enquêteurs

## 📁 Architecture Modulaire

```
enquete-prolog/
├── README.md
├── main.pl                 # Point d'entrée principal
├── data/
│   ├── personnes.pl        # Base de données des personnes
│   ├── preuves.pl          # Preuves physiques et témoignages
│   └── comportements.pl    # Comportements et antécédents
├── rules/
│   ├── scoring.pl          # Règles de calcul des scores
│   ├── classification.pl   # Classification des suspects
│   └── analysis.pl         # Règles d'analyse avancée
└── reports/
    ├── generation.pl       # Génération de rapports
    └── queries.pl          # Requêtes utiles pour les enquêteurs
```

## 🚀 Installation et Utilisation

### Prérequis
- SWI-Prolog installé sur votre système
- Connaissances de base en Prolog

### Lancement
```bash
$ swipl
?- [main].
```

### Requêtes Principales

#### Rapport Complet d'Enquête
```prolog
?- rapport_enquete.
```
Génère un rapport détaillé avec l'analyse de tous les suspects.

#### Liste des Suspects
```prolog
?- tous_suspects.
```
Affiche tous les suspects avec leurs scores de suspicion.

#### Analyse Spécifique d'un Suspect
```prolog
?- analyser_suspect(jean_martin).
```
Analyse détaillée d'un suspect particulier.

#### Identification du Suspect Principal
```prolog
?- suspect_principal(X).
```
Identifie le suspect avec le score le plus élevé.

#### Vérification de la Cohérence
```prolog
?- coherence_enquete.
```
Vérifie la cohérence des preuves contre le suspect principal.

## 📊 Système de Scoring

Le système calcule un score de suspicion basé sur 6 critères principaux :

### 1. Motifs (0-30 points)
- **Héritage** (>100k€): 30 points
- **Dettes** (>20k€): 25 points  
- **Licenciement**: 20 points
- **Rivalité professionnelle**: 15 points

### 2. Alibis (0-25 points)
- **Alibi non vérifié**: 25 points
- **Pas d'alibi déclaré**: 15 points
- **Alibi vérifié**: 0 point

### 3. Preuves Physiques (0-30+ points par preuve)
- **Haute fiabilité**: 30 points
- **Moyenne fiabilité**: 15 points
- **Faible fiabilité**: 5 points

### 4. Témoignages (20 points par témoignage)
- Chaque témoignage impliquant le suspect ajoute 20 points

### 5. Comportements Suspects (0-20 points)
- **Haute suspicion**: 20 points
- **Moyenne suspicion**: 10 points
- **Faible suspicion**: 5 points

### 6. Antécédents (0-25 points)
- **Violence conjugale**: 25 points
- **Escroquerie**: 10 points
- **Autres**: 5 points

## 📈 Classification des Suspects

- **Très Élevé** (≥80 points): Arrestation recommandée
- **Élevé** (60-79 points): Garde à vue prolongée
- **Modéré** (30-59 points): Surveillance discrète
- **Faible** (<30 points): Élargir les recherches

## 🔍 Cas d'Étude Inclus

Le système inclut une affaire complète avec :
- **Victime**: Marie Dubois
- **5 Suspects**: Jean Martin (époux), Pierre Bernard (médecin), Sophie Laurent (avocate), Thomas Moreau (jardinier), Alice Petit (secrétaire)
- **Relations complexes** entre les personnes
- **Preuves physiques** variées (ADN, empreintes, fibres)
- **Témoignages** de voisins et passants
- **Motifs** financiers et personnels

## 🛠️ Extension du Système

### Ajouter un Nouveau Suspect
```prolog
% Dans data/personnes.pl
personne(nouveau_suspect).
profession(nouveau_suspect, metier).
motif(nouveau_suspect, type_motif, montant).
```

### Ajouter de Nouveaux Types de Preuves
```prolog
% Dans data/preuves.pl
preuve_physique(nouveau_type, suspect, lieu, fiabilite).
```

### Modifier les Règles de Scoring
Les règles de calcul peuvent être ajustées dans `rules/scoring.pl` selon les besoins spécifiques de l'enquête.

## 🔧 Fonctionnalités Avancées

### Détection de Complices Potentiels
```prolog
?- lien_complice_potentiel(X, Y).
```

### Recherche par Type de Preuve
```prolog
?- preuves_type(empreintes_digitales).
```

### Analyse des Faiblesses
```prolog
?- faiblesses_enquete.
```

## 📝 Exemples de Requêtes Utiles

```prolog
% Score d'un suspect spécifique
?- score_suspicion(thomas_moreau, Score).

% Niveau de suspicion
?- niveau_suspicion(jean_martin, Niveau).

% Toutes les preuves contre un suspect
?- preuve_physique(Type, jean_martin, Lieu, Fiabilite).

% Vérification d'alibi
?- alibi_verifie(sophie_laurent, Verifie).
```

## 🎓 Applications Éducatives

Ce système peut être utilisé pour :
- **Formation des enquêteurs** : Simulation de cas réels
- **Enseignement de Prolog** : Exemple concret de système expert
- **Logique criminalistique** : Apprentissage du raisonnement déductif
- **Analyse forensique** : Compréhension de la corrélation des preuves

## 🤝 Contribution

Pour contribuer au projet :
1. Forkez le repository
2. Créez une branche pour votre fonctionnalité
3. Implémentez vos modifications dans les modules appropriés
4. Testez avec des cas d'usage variés
5. Soumettez une pull request

## 📄 Licence

Ce projet est distribué sous licence MIT. Voir le fichier LICENSE pour plus de détails.

## 👨‍💻 Auteurs

Développé comme système de démonstration pour l'apprentissage de Prolog et la simulation d'enquêtes criminelles.

---

**Note**: Ce système est purement éducatif et ne doit pas être utilisé pour de véritables enquêtes criminelles. Les conclusions générées sont basées sur des algorithmes simplifiés et ne remplacent pas l'expertise humaine en criminalistique.
