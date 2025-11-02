# Guide Rapide : Ajouter les Fichiers Modifiés sur GitHub

## Étape 1 : Installer Git (Si pas déjà fait)

1. Téléchargez Git : https://git-scm.com/download/win
2. Installez-le (gardez toutes les options par défaut)
3. **IMPORTANT** : Fermez et rouvrez PowerShell après l'installation

## Étape 2 : Configuration Initiale (Une seule fois)

Ouvrez PowerShell dans le dossier du projet et exécutez :

```powershell
# Configurez votre identité
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"
```

## Étape 3 : Créer un Dépôt sur GitHub

1. Allez sur https://github.com
2. Cliquez sur le bouton **"+"** en haut à droite > **"New repository"**
3. Nom du dépôt : `kbb-app-web`
4. Choisissez **Public** ou **Private**
5. **NE COCHEZ PAS** "Initialize with README"
6. Cliquez sur **"Create repository"**

## Étape 4 : Envoyer vos Fichiers sur GitHub

Dans PowerShell, exécutez ces commandes **une par une** :

```powershell
# 1. Initialiser Git dans le projet
git init

# 2. Ajouter tous les fichiers
git add .

# 3. Créer le premier commit
git commit -m "Initial commit - KBB Law Firm App"

# 4. Créer la branche main
git branch -M main

# 5. Lier à votre dépôt GitHub (REMPLACEZ YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/kbb-app-web.git

# 6. Envoyer sur GitHub
git push -u origin main
```

**⚠️ Important** : Remplacez `YOUR_USERNAME` par votre vrai nom d'utilisateur GitHub !

## Ajouter des Modifications Futures

Chaque fois que vous modifiez des fichiers :

```powershell
# 1. Voir les fichiers modifiés
git status

# 2. Ajouter tous les fichiers modifiés
git add .

# 3. Créer un commit avec un message descriptif
git commit -m "Description de ce que vous avez modifié"

# 4. Envoyer sur GitHub
git push
```

## Commandes Utiles

```powershell
# Voir l'historique des commits
git log --oneline

# Voir les différences avant de commiter
git diff

# Annuler les modifications non commitées
git checkout -- .

# Voir l'URL de votre dépôt distant
git remote -v
```

## Activer GitHub Pages (Hébergement Gratuit)

Après avoir poussé votre code :

1. Allez sur votre dépôt GitHub
2. Cliquez sur **Settings** > **Pages**
3. Sous "Build and deployment" :
   - Source : Sélectionnez **"GitHub Actions"**
4. Attendez 2-3 minutes
5. Votre site sera disponible sur :
   `https://YOUR_USERNAME.github.io/kbb-app-web/`

## Résolution de Problèmes

### "git n'est pas reconnu"
➜ Git n'est pas installé ou PowerShell n'a pas été redémarré
➜ Solution : Installez Git et redémarrez PowerShell

### "Authentication failed"
➜ GitHub demande un Personal Access Token
➜ Solution :
1. Allez sur https://github.com/settings/tokens
2. Cliquez sur "Generate new token" > "Generate new token (classic)"
3. Cochez "repo" et générez
4. Utilisez ce token comme mot de passe lors du push

### "Repository not found"
➜ L'URL du dépôt est incorrecte
➜ Solution : Vérifiez votre nom d'utilisateur dans l'URL

### Les fichiers ne s'affichent pas sur GitHub
➜ Le push n'a pas fonctionné
➜ Solution : Vérifiez avec `git status` et `git log`

## Fichiers Qui NE Seront PAS Envoyés

Ces fichiers sont dans `.gitignore` et resteront sur votre ordinateur :
- `node_modules/` - Dépendances (trop volumineuses)
- `.env.local` - Clés API (sensibles)
- `dist/` - Fichiers compilés (générés automatiquement)

C'est normal et voulu pour la sécurité et la performance ! ✅

---

**Besoin d'aide ?** Consultez : https://docs.github.com/fr
