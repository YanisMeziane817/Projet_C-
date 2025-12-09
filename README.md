# 📚 Système de Gestion de Bibliothèque en C++

## 🎯 Objectif
Développer un programme en C++ orienté objet pour gérer une bibliothèque.  

## 🎯 Niveau
Débutant/Intermédiaire - 
- Classes et objets
- Encapsulation (public/private)
- Fichiers séparés (.h et .cpp)
- Vectors (collections)
- Pointeurs et références
- Gestion de menu interactif

## 📁 Structure du Projet
bibliotheque/
├── main.cpp
├── Livre/
│ ├── Livre.h
│ └── Livre.cpp
├── Membre/
│ ├── Membre.h
│ └── Membre.cpp
├── Bibliotheque/
│ ├── Bibliotheque.h
│ └── Bibliotheque.cpp
└── README.md


## 🏗️ Architecture des Classes

### 1. Classe `Livre`
**Attributs privés :**
- `titre` (string)
- `auteur` (string)
- `ISBN` (string) - identifiant unique
- `disponible` (bool)
- `anneePublication` (int)

**Méthodes publiques :**
- Constructeur avec paramètres
- Getters pour tous les attributs
- Setter pour `disponible` uniquement
- `afficher()` - affiche les informations
- `estDisponible()` - retourne l'état

### 2. Classe `Membre`
**Attributs privés :**
- `nom` (string)
- `prenom` (string)
- `id` (int) - identifiant unique
- `livresEmpruntes` (vector<string>) - liste d'ISBN

**Méthodes publiques :**
- Constructeur
- Getters pour nom, prénom, id
- `emprunterLivre(string isbn)`
- `retournerLivre(string isbn)`
- `afficherLivresEmpruntes()`
- `aEmprunte(string isbn)` - vérifie possession

### 3. Classe `Bibliotheque`
**Attributs privés :**
- `livres` (vector<Livre>)
- `membres` (vector<Membre>)
- `prochainIdMembre` (int) - auto-incrémenté

**Méthodes publiques :**
- Constructeur
- Gestion livres : ajouter, supprimer, rechercher, afficher
- Gestion membres : ajouter, supprimer, rechercher, afficher
- Gestion emprunts : emprunterLivre, retournerLivre
- `afficherStatistiques()` - comptes et états

## 🎮 Fonctionnalités à Implémenter

### Menu Principal

=== GESTION DE BIBLIOTHEQUE ===

Ajouter un livre

Supprimer un livre (par ISBN)

Afficher tous les livres

Ajouter un membre

Supprimer un membre (par ID)

Afficher tous les membres

Emprunter un livre

Retourner un livre

Afficher les statistiques


### Cas d'utilisation
1. **Ajouter un livre** : Saisir titre, auteur, ISBN, année
2. **Emprunter un livre** :
   - Vérifier que le livre existe et est disponible
   - Vérifier que le membre existe
   - Mettre à jour les deux objets
3. **Retourner un livre** : Processus inverse
4. **Statistiques** : Nombre total de livres, disponibles, empruntés, membres

## 🧪 Tests à Réaliser
1. Ajouter 3 livres différents
2. Ajouter 2 membres
3. Faire emprunter un livre par un membre
4. Essayer d'emprunter un livre déjà emprunté
5. Retourner un livre
6. Supprimer un membre avec des livres empruntés
7. Rechercher un livre par ISBN

## 💡 Bonus (Optionnel)
1. **Sauvegarde automatique** : Sauvegarder dans `data.txt` à la fermeture
2. **Recherche avancée** : Par auteur ou titre partiel
3. **Catégories** : Ajouter un genre aux livres (Roman, SF, BD...)
4. **Dates** : Date d'emprunt avec calcul de retard
5. **Interface graphique** avec SFML ou Qt

## 🔧 Instructions de Compilation
```bash
# Compilation manuelle
g++ -std=c++11 main.cpp Livre/Livre.cpp Membre/Membre.cpp Bibliotheque/Bibliotheque.cpp -o bibliotheque

# Avec Makefile (optionnel)
make


