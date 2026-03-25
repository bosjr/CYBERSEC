


### `docs/creer-repo-github-windows.md`

```markdown
# Créer un repo GitHub (Windows - Ligne de commande)

## Pré-requis
- [ ] **Git** : [git-scm.com](https://git-scm.com/download/win)  
- [ ] **VS Code** : [code.visualstudio.com](https://code.visualstudio.com/)  
- [ ] **Compte GitHub**

## 1. Préparer le dossier local

```
C:\MesProjets\mon-projet\
├── README.md
├── .gitignore
└── LICENSE
```

## 2. Initialiser Git (PowerShell / VS Code Terminal)

```powershell
cd "C:\MesProjets\mon-projet"
git init
git config --global user.name "Ton Nom"
git config --global user.email "ton@email.com"
git add .
git commit -m "Premier commit"
```

## 3. Créer repo vide sur GitHub

1. GitHub → **New repository** → `mon-projet`  
2. **Public**  
3. **Ne rien cocher** (README, gitignore, license)

## 4. Lier et pousser

```powershell
git remote add origin https://github.com/tonuser/mon-projet.git
git branch -M main
git push -u origin main
git branch pour vérifier
* draft
  main
  on est bien sur draft pour travailler en local
  git checkout draft

>git status
On branch draft
Your branch is up to date with 'origin/draft'.

nothing to commit, working tree clean
```

## 5. Workflow quotidien

```powershell
# Ajouter des changements
git add .
git commit -m "Ajout feature X"

# Pousser
git push

# Récupérer les changements distants

git pull ou 
sur github.com, Create Request main from draft, Pull Request
```

## 6. GitHub Pages (bonus)

```
Settings → Pages → Source: main
Site: https://tonuser.github.io/mon-projet/
```

---

## ❌ Erreurs courantes

| Erreur | Solution |
|--------|----------|
| `src refspec main does not match any` | `git add .` → `git commit` |
| `repository not found` | Créer d'abord le repo vide sur GitHub |
| `git embedded repository` | `rmdir /s dossier\.git` |

---
