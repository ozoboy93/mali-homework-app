# 📚 Mali Homework App - Application d'accompagnement scolaire

> Une application mobile native (iOS/Android) pour assurer les devoirs à domicile des enfants de 3 à 16 ans au Mali.

![Status](https://img.shields.io/badge/Status-In%20Development-yellow)
![License](https://img.shields.io/badge/License-MIT-blue)
![Platform](https://img.shields.io/badge/Platform-iOS%20%7C%20Android-green)

## 🎯 Objectif du Projet

Créer une application innovante qui répond aux besoins éducatifs spécifiques des familles maliennes en fournissant:
- ✅ Gestion intelligente des devoirs à domicile
- ✅ Suivi de progression en temps réel
- ✅ Adaptation aux contraintes locales (connectivité, infrastructure)
- ✅ Support pour enfants de tous les niveaux (3-16 ans)

## 🏗️ Architecture Globale

```
mali-homework-app/
├── backend/                    # Serveur GraphQL (Node.js)
├── mobile-ios/                 # Application iOS native (Swift)
├── mobile-android/             # Application Android native (Kotlin)
├── database/                   # Migrations PostgreSQL
├── docs/                       # Documentation complète
├── .github/                    # Workflows CI/CD
└── scripts/                    # Scripts utilitaires
```

## 🛠️ Stack Technologique

| Composant | Technologie | Raison |
|-----------|-------------|--------|
| Backend | Node.js + Apollo Server (GraphQL) | Léger, performant, idéal pour serveur local |
| Base de données | PostgreSQL | Robuste, relationnel, gratuit |
| iOS | Swift native | Performance optimale, accès APIs complètes |
| Android | Kotlin native | Moderne, performance, moins gourmand |
| Authentification | JWT | Sécurisé, sans dépendance externe |
| Synchronisation | Apollo Client | Gestion automatique cache GraphQL |

## 📦 Prérequis

### Développement
- **Node.js** v16+ 
- **npm** ou **yarn**
- **PostgreSQL** 12+
- **Xcode** 13+ (pour iOS)
- **Android Studio** 2021+ (pour Android)
- **Git** 2.30+

### Installation Rapide

```bash
# 1. Cloner le repository
git clone https://github.com/ozoboy93/mali-homework-app.git
cd mali-homework-app

# 2. Configurer le backend
cd backend
npm install
cp .env.example .env

# 3. Configurer la base de données
docker-compose up -d
npm run migrate

# 4. Démarrer le serveur
npm run dev
```

## 📱 Fonctionnalités Principales

### Phase 1 (MVP) - Semaines 1-4
- ✅ Authentification parent (inscription/connexion)
- ✅ Création profil enfant
- ✅ Ajout de devoirs
- ✅ Affichage liste devoirs
- ✅ Marquage devoir complété

### Phase 2 - Semaines 5-8
- [ ] Tableau de bord statistiques
- [ ] Suivi de progression par matière
- [ ] Système de notifications
- [ ] Catégorisation par niveau scolaire

### Phase 3 - Semaines 9-12
- [ ] Conseils personnalisés
- [ ] Synchronisation offline
- [ ] Support multi-enfants
- [ ] Personnalisation thème

### Phase 4 (Futur)
- [ ] Intégration IA
- [ ] Tutoriels vidéo
- [ ] Connexion enseignants
- [ ] Mode avancé hors ligne

## 🗂️ Structure du Backend

```
backend/
├── src/
│   ├── schema/              # Définitions GraphQL
│   ├── models/              # Modèles Sequelize
│   ├── middleware/          # Auth, validation
│   ├── services/            # Logique métier
│   ├── utils/               # Helpers
│   └── index.ts
├── migrations/              # Migrations BD
├── docker-compose.yml
└── package.json
```

## 🔐 Authentification & Sécurité

- JWT (JSON Web Tokens) pour les sessions
- Hachage bcrypt pour les mots de passe
- CORS configuré pour mobile
- Validation des entrées GraphQL
- Rate limiting sur les endpoints sensibles

## 🌍 Considérations Mali-Spécifiques

| Défi | Solution |
|------|----------|
| Connectivité instable | Synchronisation offline avec SQLite local |
| Coûts data élevés | GraphQL optimisé, compression images |
| Appareils anciens | Code natif léger (Kotlin/Swift) |
| Multilinguisme | Support français + langues locales |
| Infrastructure serveur | Docker + PostgreSQL sur machine locale |

## 🚀 Démarrage Rapide

### Backend
```bash
cd backend
npm install
npm run dev        # Démarre sur http://localhost:4000
```

### Accéder à GraphQL Playground
```
http://localhost:4000/graphql
```

## 📚 Documentation

- [Backend Setup Guide](docs/backend-setup.md)
- [API GraphQL Reference](docs/graphql-schema.md)
- [iOS Development](docs/ios-setup.md)
- [Android Development](docs/android-setup.md)
- [Git Workflow](docs/git-workflow.md)
- [Database Schema](database/schema.sql)

## 🔄 Git Workflow

### Branches Principales
- `main` : Production stable
- `develop` : Intégration
- `feature/*` : Nouvelles fonctionnalités
- `bugfix/*` : Corrections de bugs

### Créer une Feature

```bash
git checkout develop
git pull origin develop
git checkout -b feature/description-courte
# Faire les modifications
git add .
git commit -m "feat(module): Description"
git push origin feature/description-courte
```

## 📝 Conventions de Commit

```
feat(auth): Ajouter login parent
fix(homework): Corriger calcul date limite
docs(readme): Mettre à jour installation
test(progress): Ajouter tests unitaires
style(ui): Formater contraintes Layout
refactor(api): Simplifier resolver GraphQL
```

## 📄 License

MIT License - Voir [LICENSE](LICENSE) pour détails

## 🎓 Ressources Utiles

- [Apollo Server Documentation](https://www.apollographql.com/docs/apollo-server/)
- [Apollo iOS Client](https://www.apollographql.com/docs/ios/)
- [Apollo Android](https://www.apollographql.com/docs/android/)
- [Swift.org Guides](https://swift.org/getting-started/)
- [Kotlin for Android](https://kotlinlang.org/docs/android-overview.html)
- [PostgreSQL Tutorials](https://www.postgresql.org/docs/current/tutorial.html)

---

**Version** : 0.1.0  
**Dernière mise à jour** : Septembre 2026  
**Statut** : En développement 🚀
