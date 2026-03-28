HTB : https://hackthedome.com/android-fundamentals/



# 1️⃣ Installation du SDK et des outils nécessaires

### 📥 Télécharger

1. Installer **Android Studio** depuis le site officiel.
2. Lors de l’installation, sélectionner :

   * **Android SDK**
   * **Android SDK Platform-Tools**
   * **Android SDK Build-Tools**
   * **Intel HAXM (optionnel pour accélération)**

---

### 🔧 Vérifier l’installation

Le SDK se trouve par défaut ici :

```
C:\Users\<username>\AppData\Local\Android\Sdk
```

* `platform-tools` → contient `adb`
* `emulator` → contient l’émulateur
* `system-images` → images Android

---

# 2️⃣ Création d’un AVD (Device Android Virtual)

### Méthode Android Studio (interface graphique)

1. **Device Manager** (volet droit ou **Shift + Shift → Device Manager**)
2. **Create Device**

   * Modèle : Medium Phone ou Pixel 3a
3. **Next → System Image**

   * Sélectionner **Other Images**
   * Image à choisir :

     ```
     Android 11 (API 30) – Google APIs – x86_64
     ```
   * ❌ Ne pas utiliser Play Store
4. **Finish**

---

### Méthode ligne de commande (si cmdline-tools installés)

```powershell
cd "C:\Users\<username>\AppData\Local\Android\Sdk\cmdline-tools\latest\bin"

.\sdkmanager "system-images;android-30;google_apis;x86_64"
.\avdmanager create avd -n HTB_API30 -k "system-images;android-30;google_apis;x86_64" --device "pixel"
```

Vérifier :

```powershell
cd "C:\Users\<username>\AppData\Local\Android\Sdk\emulator"
.\emulator -list-avds
```

Lancer l’AVD :

```powershell
.\emulator -avd HTB_API30
```

---

# 3️⃣ Vérifier ADB et le device

```powershell
cd "C:\Users\<username>\AppData\Local\Android\Sdk\platform-tools"
.\adb devices
```

* Doit afficher `emulator-5554   device`

---

# 4️⃣ Installer l’APK

```powershell
.\adb install myapp.apk
```

Vérifier :

```powershell
.\adb shell pm list packages | findstr hackthebox
```

---

# 5️⃣ Lancer l’application

```powershell
.\adb shell monkey -p com.hackthebox.myapp -c android.intent.category.LAUNCHER 1
```

---

# 6️⃣ Extraction des flags

### 🔑 Flag 1 – Stockage interne (requiert root)

```powershell
.\adb root
.\adb shell cat /data/data/com.hackthebox.myapp/files/flag.txt
```

### 📦 Flag 2 – Stockage externe (pas de root)

```powershell
.\adb pull /sdcard/Download/flag.zip
Expand-Archive .\flag.zip
type flag.txt
```

---

# 7️⃣ Commandes utiles supplémentaires

* Lister fichiers internes :

```powershell
.\adb shell ls -R /data/data/com.hackthebox.myapp/
```

* Vérifier shared_prefs :

```powershell
.\adb shell cat /data/data/com.hackthebox.myapp/shared_prefs/*.xml
```

* Vérifier bases SQLite :

```powershell
.\adb shell ls /data/data/com.hackthebox.myapp/databases/
.\adb shell sqlite3 /data/data/com.hackthebox.myapp/databases/<db>.db ".tables"
```

* Rechercher flags :

```powershell
.\adb shell grep -R "flag" /data/data/com.hackthebox.myapp/
```

---

# ✅ Résumé rapide

| Étape           | Outil                | Commande / Action                                   |
| --------------- | -------------------- | --------------------------------------------------- |
| Installer SDK   | Android Studio       | Installer Android SDK & Platform Tools              |
| Créer AVD       | Android Studio / CLI | Device Manager → Create Device / `avdmanager`       |
| Lancer AVD      | CLI                  | `emulator -avd <name>`                              |
| Vérifier device | CLI                  | `adb devices`                                       |
| Installer APK   | CLI                  | `adb install myapp.apk`                             |
| Lancer APK      | CLI                  | `adb shell monkey -p ...`                           |
| Flag interne    | CLI                  | `adb root && adb shell cat /data/data/.../flag.txt` |
| Flag externe    | CLI                  | `adb pull /sdcard/Download/flag.zip` + extraire     |

Ressource : 
