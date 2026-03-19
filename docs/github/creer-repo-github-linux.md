Voici **`docs/github/creer-repo-github-linux.md`** prêt à copier :

***

### `docs/creer-repo-linux.md`

```markdown
# Créer un repo GitHub (Linux - Terminal)

## Pré-requis
- [ ] **Git** : `sudo apt install git` (Ubuntu/Debian)  
- [ ] **Compte GitHub**

## 1. Préparer le dossier

```bash
mkdir mon-projet
cd mon-projet
# Créer README.md, .gitignore, LICENSE
```

## 2. Configurer Git (une seule fois)

```bash
git config --global user.name "Ton Nom"
git config --global user.email "ton@email.com"
```

## 3. Initialiser et premier commit

```bash
git init
git add .
git commit -m "Premier commit"
```

## 4. Créer repo vide sur GitHub

GitHub → **New repository** → `mon-projet` → **Public** → **sans README**.

## 5. Lier et pousser

```bash
git remote add origin https://github.com/tonuser/mon-projet.git
git branch -M main
git push -u origin main
```

## 6. Workflow quotidien

```bash
# Modifier des fichiers
vim README.md

# Ajouter + commiter + pousser
git add .
git commit -m "Ajout feature X"
git push

# Raccourci 1 ligne
git add . && git commit -m "msg" && git push
```

## 7. GitHub Pages

```
Settings → Pages → Source: main
Site: https://tonuser.github.io/mon-projet/
```

---

## ❌ Erreurs courantes

| Erreur | Solution |
|--------|----------|
| `src refspec main does not match any` | `git add . && git commit -m "msg"` |
| `repository not found` | Créer repo vide sur GitHub d'abord |
| `git embedded repo` | `rm -rf sous-dossier/.git` |

---
