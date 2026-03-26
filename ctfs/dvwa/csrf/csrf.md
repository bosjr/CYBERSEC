
```markdown
# DVWA CSRF (Low → Medium → High)

## 🔎 Rappel CSRF
CSRF = forcer un utilisateur déjà authentifié à exécuter une action (ex: changer son mot de passe) via une requête forgée (lien, image, formulaire caché). [web:272]


## 🟢 Low

### Fonctionnement
- Formulaire "Change password" sans token CSRF, seulement `password_new` et `password_conf`. [web:272][web:269]
- Requête en `GET` avec les paramètres dans l’URL.

### Exploit
1. Change ton mot de passe normalement.
2. Copie l’URL dans la barre (elle contient `password_new=...&password_conf=...`). [web:272]
3. Colle-la dans un `<img>` ou un lien malveillant, par exemple :

```html
<a href="http://dvwa/vulnerabilities/csrf/?password_new=hacked&password_conf=hacked&Change=Change">
Clique ici pour voir une image
</a>
Si la victime est connectée, son mot de passe est changé.



## 🟢 Low

### Fonctionnement
- Formulaire "Change password" sans token CSRF, seulement `password_new` et `password_conf`. [web:272][web:269]
- Requête en `GET` avec les paramètres dans l’URL.

### Exploit
1. Change ton mot de passe normalement.
2. Copie l’URL dans la barre (elle contient `password_new=...&password_conf=...`). [web:272]
3. Colle-la dans un `<img>` ou un lien malveillant, par exemple :

```html
<a href="http://dvwa/vulnerabilities/csrf/?password_new=hacked&password_conf=hacked&Change=Change">
Clique ici pour voir une image
</a>
```

Si la victime est connectée, son mot de passe est changé.

---

## 🟡 Medium

### Protection ajoutée
- Vérification de l’en-tête `Referer` : la requête doit venir du site DVWA lui‑même. [web:271]

### Idée d’exploit
- Utiliser une autre vuln (par ex. XSS réfléchi) pour injecter le formulaire CSRF **depuis** DVWA, donc avec un `Referer` correct. [web:271]
- Exemple simple à décrire pour tes étudiants :  
  1. Trouver une page XSS.  
  2. Injecter un formulaire auto‑submit qui POSTe vers `/vulnerabilities/csrf/`.  

(Tu pourras détailler quand tu feras le lab XSS.)

---

## 🟠 High

### Protection
- Token CSRF dans le formulaire (`user_token` ou similaire), vérifié côté serveur. [web:264][web:266]
- Le token change à chaque requête.

### Idée d’explication
- Montrer le token dans le code source du formulaire.
- Montrer qu’un simple lien ou formulaire statique échoue, car le token devient invalide.
- Introduire le concept de **token synchronisé** et de **SameSite cookies** en bonus. [web:270][web:276]

---

## 🛡️ Bonnes pratiques (défense)

- Utiliser les protections CSRF intégrées du framework (Django, Laravel, Symfony, Spring, etc.). [web:270][web:276]  
- Ajouter un **token CSRF imprévisible** dans tous les formulaires modifiant l’état, et vérifier le token côté serveur. [web:273]  
- Activer l’attribut **SameSite** sur les cookies de session (`Lax` ou `Strict`) pour limiter l’envoi cross‑site. [web:270]  
- Éviter d’utiliser **GET** pour des actions sensibles (utiliser POST + token). [web:262][web:273]
```

***

Dans GitHub Desktop (toujours sur **draft**, comme sur ta capture) :  
1) Crée `ctfs/dvwa/csrf.md` avec ce squelette.  
2) Ajoute tes captures Low, puis Medium/High quand tu feras les tests.  
3) Commit → Push sur `draft`, puis plus tard tu feras la Pull Request vers `main` comme pour les autres.

Tu préfères que je t’aide à détailler d’abord le **Low** avec un exemple HTML complet que tes étudiants pourront ouvrir dans un fichier `.html` local ?