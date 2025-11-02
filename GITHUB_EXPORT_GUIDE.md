# Guide d'Exportation vers GitHub

Ce guide vous explique comment exporter ce projet vers GitHub.

## Prérequis

1. **Installer Git** (si ce n'est pas déjà fait)
   - Téléchargez Git depuis : https://git-scm.com/download/win
   - Installez-le avec les options par défaut
   - Redémarrez votre terminal après l'installation

2. **Créer un compte GitHub**
   - Rendez-vous sur : https://github.com
   - Créez un compte si vous n'en avez pas

## Étapes pour Exporter le Projet

### 1. Initialiser le Dépôt Git Local

Ouvrez PowerShell dans le dossier du projet et exécutez :

```powershell
git init
git add .
git commit -m "Initial commit - KBB App"
```

### 2. Créer un Nouveau Dépôt sur GitHub

1. Connectez-vous à GitHub
2. Cliquez sur le bouton **"New"** (ou le + en haut à droite)
3. Nommez votre dépôt : `kbb-app-web`
4. Choisissez **Public** ou **Private**
5. **NE PAS** initialiser avec README, .gitignore ou licence (nous les avons déjà)
6. Cliquez sur **"Create repository"**

### 3. Lier le Dépôt Local à GitHub

Copiez l'URL de votre nouveau dépôt GitHub, puis exécutez :

```powershell
# Remplacez YOUR_USERNAME par votre nom d'utilisateur GitHub
git remote add origin https://github.com/YOUR_USERNAME/kbb-app-web.git
git branch -M main
git push -u origin main
```

### 4. Vérifier que tout est en Ligne

Retournez sur GitHub et rafraîchissez la page. Vous devriez voir tous vos fichiers !

## Commandes Git Utiles pour la Suite

### Sauvegarder vos Modifications

```powershell
# Ajouter tous les fichiers modifiés
git add .

# Créer un commit avec un message
git commit -m "Description de vos modifications"

# Envoyer vers GitHub
git push
```

### Vérifier l'État de votre Dépôt

```powershell
# Voir les fichiers modifiés
git status

# Voir l'historique des commits
git log --oneline
```

### Ignorer des Fichiers

Les fichiers suivants sont déjà dans `.gitignore` et ne seront PAS envoyés sur GitHub :
- `node_modules/` (dépendances - trop volumineuses)
- `.env.local` (clés API - sensibles)
- `dist/` (fichiers compilés)

## Configuration Git (Première Utilisation)

Si c'est la première fois que vous utilisez Git, configurez votre identité :

```powershell
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"
```

## Résolution de Problèmes

### Erreur : "git n'est pas reconnu"
- Git n'est pas installé. Installez-le depuis https://git-scm.com
- Redémarrez votre terminal après l'installation

### Erreur d'Authentification GitHub
- Utilisez un Personal Access Token au lieu d'un mot de passe
- Créez-le sur : https://github.com/settings/tokens
- Utilisez-le comme mot de passe lors du push

### Le Push est Rejeté
```powershell
# Récupérer les dernières modifications
git pull origin main --rebase

# Puis réessayer le push
git push
```

## Fichiers Importants Créés

✅ `.gitignore` - Fichiers à ignorer par Git
✅ `.env.example` - Exemple de configuration
✅ `LICENSE` - Licence MIT
✅ `README.md` - Documentation du projet
✅ `GITHUB_EXPORT_GUIDE.md` - Ce guide

## Prochaines Étapes

### Déployer sur GitHub Pages (Hébergement Gratuit)

Une fois votre code poussé sur GitHub, activez GitHub Pages :

1. **Activer GitHub Pages**
   - Allez sur votre dépôt GitHub
   - Cliquez sur **Settings** > **Pages**
   - Sous "Build and deployment" :
     - Source : Sélectionnez **GitHub Actions**
   - Le déploiement se fera automatiquement à chaque push !

2. **Accéder à votre Application**
   - Après quelques minutes, votre app sera accessible sur :
   - `https://YOUR_USERNAME.github.io/kbb-app-web/`
   - L'URL exacte s'affichera dans Settings > Pages

3. **Note Importante**
   - Le premier déploiement peut prendre 2-5 minutes
   - Les déploiements suivants sont automatiques à chaque push
   - Le workflow de déploiement est dans `.github/workflows/deploy.yml`

### Autres Options

1. **Ajouter des Collaborateurs**
   - Settings > Collaborators
   - Invitez d'autres développeurs

2. **Protéger la Branche Main**
   - Settings > Branches
   - Ajoutez des règles de protection

## Résoudre le Problème d'Écran Blanc

Si vous voyez un écran blanc sur GitHub Pages :

✅ **C'est déjà corrigé !** Le fichier `vite.config.ts` a été configuré avec `base: './'`

Cela garantit que tous les chemins sont relatifs et fonctionnent sur GitHub Pages.

Si le problème persiste :
1. Vérifiez que GitHub Pages est activé dans Settings > Pages
2. Attendez 2-3 minutes après le push
3. Videz le cache de votre navigateur (Ctrl+Shift+R)
4. Vérifiez les Actions dans l'onglet "Actions" de votre dépôt

Bon développement ! 🚀
