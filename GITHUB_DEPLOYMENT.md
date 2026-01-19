# 🚀 Instructions de Déploiement GitHub

## 📦 Fichiers du Repository

Tous les fichiers sont prêts dans `/mnt/user-data/outputs/` :

```
ai-usage-stats-europe/
├── index.html          # Application principale (standalone)
├── README.md           # Documentation complète
├── LICENSE             # MIT License
├── .gitignore          # Règles Git
├── CONTRIBUTING.md     # Guide pour contributeurs
└── TECHNICAL.md        # Documentation technique
```

## 🔧 Setup GitHub Repository

### Étape 1: Créer le Repository

1. Va sur [GitHub.com](https://github.com)
2. Clique sur "+" → "New repository"
3. **Repository name:** `ai-usage-stats-europe`
4. **Description:** `Interactive dashboard for Claude AI usage statistics across Europe`
5. **Visibility:** Public (ou Private selon préférence)
6. ❌ **NE PAS** cocher "Add README" (on a déjà le nôtre)
7. Clique "Create repository"

### Étape 2: Initialiser le Repository Localement

```bash
# Créer un nouveau dossier
mkdir ai-usage-stats-europe
cd ai-usage-stats-europe

# Initialiser Git
git init

# Copier tous les fichiers du outputs dans ce dossier
# (index.html, README.md, LICENSE, .gitignore, CONTRIBUTING.md, TECHNICAL.md)

# Ajouter tous les fichiers
git add .

# Premier commit
git commit -m "Initial commit: AI Usage Statistics Dashboard v1.0.0"

# Ajouter le remote (remplace YOUR_USERNAME par ton username GitHub)
git remote add origin https://github.com/YOUR_USERNAME/ai-usage-stats-europe.git

# Pousser sur GitHub
git branch -M main
git push -u origin main
```

### Étape 3: Configuration GitHub Pages (Optionnel)

Pour héberger gratuitement sur GitHub Pages:

1. Va dans **Settings** de ton repo
2. Scroll jusqu'à **Pages** (dans le menu gauche)
3. **Source:** Deploy from a branch
4. **Branch:** main
5. **Folder:** / (root)
6. Clique "Save"
7. Attends 2-3 minutes
8. Ton site sera disponible à: `https://YOUR_USERNAME.github.io/ai-usage-stats-europe/`

## 🎯 Commandes Git Utiles

### Mettre à jour le code

```bash
# Après avoir modifié des fichiers
git add index.html
git commit -m "fix: correct back button behavior"
git push
```

### Créer une nouvelle version

```bash
# Tag pour version
git tag -a v1.0.1 -m "Version 1.0.1 - Bug fixes"
git push origin v1.0.1
```

### Voir l'historique

```bash
git log --oneline
```

## 📝 Checklist Post-Déploiement

- [ ] Repository créé sur GitHub
- [ ] Tous les fichiers pushés
- [ ] README.md s'affiche correctement
- [ ] LICENSE visible
- [ ] GitHub Pages configuré (si souhaité)
- [ ] Lien ajouté dans le README (si GitHub Pages activé)
- [ ] Repository ajouté dans ton profil/portfolio

## 🔄 Workflow de Mise à Jour

### Pour mettre à jour les données

1. Modifie `index.html` → section `allData`
2. Update la date `last_updated`
3. Commit & push:
```bash
git add index.html
git commit -m "data: update statistics to Feb 2026"
git push
```

### Pour ajouter des features

1. Crée une branche:
```bash
git checkout -b feature/new-chart-type
```

2. Fais tes modifications
3. Commit:
```bash
git add .
git commit -m "feat: add time series chart"
```

4. Push la branche:
```bash
git push origin feature/new-chart-type
```

5. Crée une Pull Request sur GitHub
6. Merge dans main

## 🌐 URLs à Noter

Après déploiement, tu auras:

- **Repository:** `https://github.com/YOUR_USERNAME/ai-usage-stats-europe`
- **GitHub Pages:** `https://YOUR_USERNAME.github.io/ai-usage-stats-europe/`
- **Production (Umso):** `https://thinkingahead.com/data-statistics`

## 🔗 Intégration dans ton Portfolio

Ajoute ce projet dans:
- Ton site Thinking Ahead
- Ton profil GitHub
- Ton LinkedIn
- Ton portfolio de projets

## 📧 Support

Si tu as des questions sur le déploiement GitHub:
- [GitHub Docs - Creating a repo](https://docs.github.com/en/get-started/quickstart/create-a-repo)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)

## ✅ Vérification Finale

Après le push, vérifie que:
1. Tous les fichiers sont visibles sur GitHub
2. Le README s'affiche correctement
3. Le code est bien formaté
4. Les liens fonctionnent
5. GitHub Pages est accessible (si activé)

---

🎉 **C'est prêt!** Ton repository est maintenant public et professionnel.
