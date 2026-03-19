 `docs/creer-repo-gitdesktop-win-linux-mac.md` **universel** :

***

```markdown
# Créer un repo avec GitHub Desktop (Windows/Linux/Mac)

[![GitHub Desktop](https://img.shields.io/badge/GitHub-Desktop-181717?style=flat&logo=github)](https://desktop.github.com/)

## Pré-requis
- [ ] **GitHub Desktop** : [Télécharger](https://desktop.github.com/)  
- [ ] **Compte GitHub** : [github.com](https://github.com)  
- [ ] **Éditeur** : VS Code, Notepad++, Vim...

## 1. Créer le dossier local

```
**Windows** : C:\MesProjets\mon-projet\
**Linux/Mac** : ~/MesProjets/mon-projet/
├── README.md          (description du projet)
├── .gitignore         (fichiers à ignorer)
└── LICENSE            (licence MIT/CC0)
```

**Exemple README.md** :
```markdown
# Mon Projet
Description rapide du projet.
```

## 2. GitHub Desktop : Ajouter le repo local

1. Ouvrir **GitHub Desktop**  
2. **File → Add an existing repository from your hard drive**  
3. **"Choose..."** → sélectionner `mon-projet`  
4. **"Add repository"**

```
✅ Repository added: mon-projet
```

## 3. Premier commit

```
📁 Changes (3 files)
✅ README.md              [Added]
✅ .gitignore             [Added]
✅ LICENSE                [Added]

Summary : "Premier commit - structure initiale"
→ Commit to main
```

## 4. Publier sur GitHub

```
1. Bouton "Publish repository" (haut)
2. Name : mon-projet
3. Organization : tonuser (ou org)
4. ✅ Public
5. Publish repository
```

**Résultat** : `https://github.com/tonuser/mon-projet`

## 5. Workflow quotidien

```
1. Modifier/ajouter fichiers
2. GitHub Desktop → Changes (auto-détecté)
3. ✅ Cocher les fichiers
4. Summary : "Ajout lab X" / "Fix bug Y"
5. Commit to main → Push origin
```

## 6. GitHub Pages (site web gratuit)

```
Repo → Settings → Pages
Source : Deploy from a branch → main → Save
Site : https://tonuser.github.io/mon-projet/
```

---

## 💡 Raccourcis GitHub Desktop

| Action | Raccourci |
|--------|-----------|
| Voir changements | `Ctrl+Shift+G` |
| Commit + Push | `Ctrl+Enter` |
| Ouvrir GitHub | `Ctrl+Shift+F` |
| Rafraîchir | `F5` |

---

## ❌ Erreurs courantes & Solutions

| Erreur | Cause | Solution |
|--------|-------|----------|
| `No local changes` | Pas de fichiers modifiés | Ajouter/éditer fichiers |
| Dossiers non détectés | Cache | `F5` ou Repository → Pull |
| "Git embedded repo" | Sous-dossier cloné | Supprimer `dossier/.git` |
| "Branch ahead" | Commits locaux non poussés | `Push origin` |

---

