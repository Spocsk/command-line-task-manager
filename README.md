# Gestionnaire de Tâches CLI en Go

Un gestionnaire de tâches moderne en ligne de commande développé en Go, permettant une gestion efficace des tâches quotidiennes avec persistance des données.

## 📋 Table des matières

- [Présentation](#présentation)
- [Fonctionnalités](#fonctionnalités)
- [Spécifications techniques](#spécifications-techniques)
- [Installation](#installation)
- [Architecture](#architecture)
- [Plan d'implémentation](#plan-dimplémentation)
- [Critères de qualité](#critères-de-qualité)
- [Développement futur](#développement-futur)
- [Contribuer](#contribuer)

## 🎯 Présentation

### Objectif
Développer une application de gestion de tâches en ligne de commande permettant aux utilisateurs de gérer efficacement leurs tâches quotidiennes.

### Public cible
- Développeurs préférant les outils en ligne de commande
- Utilisateurs cherchant un gestionnaire de tâches simple et efficace
- Personnes privilégiant les interfaces en ligne de commande

## ✨ Fonctionnalités

### Gestion des tâches
- **Création de tâches**
  - Titre (obligatoire)
  - Description (optionnelle)
  - Statut (en attente/en cours/terminée)
  - Priorité (échelle de 1 à 5)
  - Date d'échéance
  - Tags/étiquettes

- **Modification des tâches**
  - Mise à jour du statut
  - Modification de la description
  - Ajout/suppression de tags
  - Changement de priorité

- **Suppression de tâches**
  - Suppression par ID
  - Confirmation requise

- **Consultation**
  - Liste complète
  - Filtrage par statut
  - Filtrage par priorité
  - Recherche par tags

### Persistance des données
- Stockage au format JSON
- Gestion automatique des sauvegardes

## 🔧 Spécifications techniques

### Prérequis
- Go 1.21+
- Pas de dépendances externes requises

### Packages Go utilisés
- `encoding/json` : Gestion du format JSON
- `time` : Gestion des dates
- `os` : Opérations fichiers
- `fmt` : Formatage des sorties
- `testing` : Tests unitaires

### Structure de données principale
```go
type Task struct {
    ID          int
    Title       string
    Description string
    Status      string
    Priority    int
    CreatedAt   time.Time
    DueDate     time.Time
    Tags        []string
}
```

## 📦 Installation

1. Cloner le repository
```bash
git clone https://github.com/votre-username/task-manager-go
cd task-manager-go
```

2. Compiler le projet
```bash
go build -o task-manager
```

3. Exécuter l'application
```bash
./task-manager
```

## 🏗 Architecture

```
project/
├── cmd/
│   └── main.go
├── internal/
│   ├── models/
│   │   └── task.go
│   ├── storage/
│   │   └── json_storage.go
│   └── manager/
│       └── task_manager.go
├── pkg/
│   └── utils/
│       └── date_utils.go
└── tests/
    └── manager_test.go
```

## 📅 Plan d'implémentation

### Phase 1 : Configuration de base
- [ ] Création de la structure du projet
- [ ] Mise en place du système de modules Go
- [ ] Configuration du gestionnaire de versions

### Phase 2 : Fonctionnalités de base
- [ ] Implémentation de la structure Task
- [ ] Création du TaskManager
- [ ] Développement des opérations CRUD basiques

### Phase 3 : Persistance
- [ ] Implémentation du stockage JSON
- [ ] Gestion des erreurs de fichier
- [ ] Optimisation des opérations de lecture/écriture

### Phase 4 : Interface utilisateur
- [ ] Développement du menu principal
- [ ] Implémentation des commandes utilisateur
- [ ] Validation des entrées utilisateur

### Phase 5 : Tests et documentation
- [ ] Écriture des tests unitaires
- [ ] Documentation du code
- [ ] Création du README et documentation utilisateur

## 🎯 Critères de qualité

### Performance
- Temps de réponse < 100ms pour les opérations basiques
- Utilisation mémoire < 50MB
- Gestion efficace des fichiers JSON

### Fiabilité
- Validation des données entrantes
- Gestion appropriée des erreurs
- Sauvegarde systématique des modifications

### Maintenabilité
- Documentation claire du code
- Tests unitaires avec couverture > 80%
- Respect des bonnes pratiques Go

## 🚀 Développement futur

### Améliorations techniques
- Migration vers une base de données SQL
- Ajout d'une API REST
- Interface web avec Gin

### Nouvelles fonctionnalités
- Système de rappels/notifications
- Sous-tâches
- Partage de tâches
- Export des données (CSV, PDF)

## 🤝 Contribuer

Les contributions sont les bienvenues ! Voici comment vous pouvez participer :

1. Fork le projet
2. Créer une branche (`git checkout -b feature/AmazingFeature`)
3. Commit vos changements (`git commit -m 'Add some AmazingFeature'`)
4. Push vers la branche (`git push origin feature/AmazingFeature`)
5. Ouvrir une Pull Request

## 📝 Livrables

### Code source
- Repository Git complet
- Documentation du code
- Tests unitaires

### Documentation
- README détaillé
- Guide d'installation
- Manuel d'utilisation
- Documentation API (si implémentée)

### Binaires
- Exécutable Linux
- Exécutable Windows
- Exécutable MacOS

## 📄 Licence

Distribué sous la licence MIT. Voir `LICENSE` pour plus d'informations.
