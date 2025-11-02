# KBB App - Application de Gestion de Cabinet d'Avocats

Bienvenue sur le dépôt de KBB App, une application web moderne conçue pour la gestion complète d'un cabinet d'avocats. Cette application a été développée comme une démonstration interactive et fonctionnelle.

## ✨ Fonctionnalités Principales

- **Tableau de Bord Intuitif** : Vue d'ensemble des dossiers actifs, des clients et des événements à venir.
- **Gestion des Clients** : Ajout, consultation et gestion de la base de données clients.
- **Gestion des Dossiers** : Création de dossiers détaillés avec liaison aux clients, gestion des tâches, des statuts et ajout de pièces jointes.
- **Module Événements** : Suivi des audiences, conférences, colloques et autres événements importants.
- **Agenda & Tâches** : Création et suivi des tâches liées aux dossiers, avec échéances et assignations.
- **Messagerie Interne** : Un système de chat pour la communication entre les membres du cabinet.
- **Facturation** : Enregistrement et suivi des factures, avec calcul automatique des montants restants et gestion des statuts de paiement.
- **Gestion des Avocats** : Répertoire détaillé des avocats du cabinet avec leurs informations professionnelles et de contact.
- **Panneau d'Administration** : Une section de gestion centralisée pour modifier ou supprimer n'importe quelle donnée de l'application.
- **Exportation en PDF** : Génération de rapports PDF pour les listes de clients et de dossiers.
- **Authentification** : Une interface de connexion pour sécuriser l'accès à l'application.
- **Persistance des Données** : Toutes les données sont sauvegardées localement dans votre navigateur (`localStorage`), ce qui rend la démo entièrement fonctionnelle et persistante entre les sessions.

## 💻 Technologies Utilisées

- **React 19** - Framework JavaScript pour l'interface utilisateur
- **TypeScript** - Typage statique pour un code plus robuste
- **Vite** - Build tool rapide et moderne
- **Tailwind CSS** - Framework CSS utilitaire
- **jsPDF** & **jspdf-autotable** - Génération de documents PDF
- **LocalStorage** - Persistance des données côté client

## 🚀 Installation et Lancement

### Prérequis

- Node.js (version 16 ou supérieure)
- npm ou yarn

### Installation

1. **Clonez le dépôt**
```bash
git clone https://github.com/votre-username/kbb-app-web.git
cd kbb-app-web
```

2. **Installez les dépendances**
```bash
npm install
```

3. **Configurez les variables d'environnement** (optionnel)
```bash
cp .env.example .env.local
```
Modifiez `.env.local` et ajoutez vos clés API si nécessaire.

4. **Lancez l'application en mode développement**
```bash
npm run dev
```

L'application sera accessible à l'adresse : `http://localhost:3000`

### Scripts Disponibles

- `npm run dev` - Lance le serveur de développement
- `npm run build` - Compile l'application pour la production
- `npm run preview` - Prévisualise la version de production

## 📁 Structure du Projet

```
kbb-app-web/
├── public/           # Fichiers statiques (images, logo)
├── src/
│   ├── components/   # Composants React réutilisables
│   ├── pages/        # Pages de l'application
│   ├── data/         # Données mock
│   ├── hooks/        # Hooks React personnalisés
│   └── types/        # Types TypeScript
├── index.html        # Point d'entrée HTML
├── index.tsx         # Point d'entrée React
└── vite.config.ts    # Configuration Vite
```

## 🔒 Sécurité

- Ne commitez jamais le fichier `.env.local` qui contient vos clés API
- Les données sont stockées uniquement dans le localStorage du navigateur
- Pour une utilisation en production, implémentez un backend sécurisé

## 📝 Licence

Ce projet est à usage éducatif et de démonstration.

## 👥 Contributeurs

KBB Law Firm SCP

## 🤝 Contribution

Les contributions sont les bienvenues ! N'hésitez pas à ouvrir une issue ou une pull request.

---

Développé avec ❤️ pour KBB Law Firm
```
