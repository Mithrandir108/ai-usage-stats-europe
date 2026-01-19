# 🔧 Configuration GitHub Repository

## Étape 1: Ajouter .gitattributes

```bash
# Dans ton dossier local du projet
git add .gitattributes
git commit -m "chore: force JavaScript language detection"
git push
```

**Attends 2-3 minutes** que GitHub recalcule les langages du repo.

## Étape 2: Mettre à jour la Description

1. Va sur ton repo GitHub
2. Clique sur ⚙️ (Settings) ou sur "Edit" à côté de "About"
3. **Description:** 
```
Interactive data visualization analyzing AI usage trends and professional adoption patterns across Europe
```

## Étape 3: Ajouter les Topics

Dans la même section "About", ajoute ces **Topics** :

```
javascript
vanilla-js
chartjs
data-visualization
svg
interactive-map
ai-statistics
europe
anthropic
claude-ai
dashboard
analytics
b2b-saas
```

Clique "Save changes"

## Étape 4: Vérifier le Badge de Langage

Après avoir push le `.gitattributes` :
- Rafraîchis la page du repo
- Le badge devrait maintenant afficher "JavaScript" au lieu de "HTML"
- Les statistiques de langage devraient refléter JavaScript comme principal

## Étape 5: Pin le Repository (Optionnel)

Pour le mettre en avant sur ton profil :
1. Va sur ton profil GitHub
2. Clique "Customize your pins"
3. Sélectionne "ai-usage-stats-europe"
4. Save

## ✅ Résultat Attendu

Après ces étapes, ton repo affichera :
- 🟨 **JavaScript** comme langage principal
- Description professionnelle
- Topics pertinents pour la découvrabilité
- Technologies valorisées visibles

## 📝 Note

Si le badge ne change pas immédiatement après le push du `.gitattributes`, GitHub peut prendre jusqu'à 24h pour recalculer. Tu peux forcer en :
- Faisant un commit vide: `git commit --allow-empty -m "trigger rebuild"`
- Ou en attendant que GitHub recalcule automatiquement
