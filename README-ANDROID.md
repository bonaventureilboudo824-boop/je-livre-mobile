# Je Livre — App Android (Capacitor)

Ce dossier contient un vrai projet Android. Il enveloppe exactement la même
app web déjà en ligne (le fichier `www/index.html` est une copie de
`je-livre-prototype.html`) — elle continue donc de parler à la même base
Firebase que le site, sans rien dupliquer.

**Aucune installation sur votre ordinateur n'est nécessaire.** La compilation
se fait automatiquement par GitHub lui-même (fichier
`.github/workflows/android-build.yml`, déjà inclus) — vous n'avez besoin que
du Cloud Shell, exactement comme pour le reste du projet.

## Mettre ce projet en ligne (une seule fois)

1. Sur GitHub, créez un nouveau dépôt vide nommé `je-livre-mobile` (bouton
   vert "New" sur votre page de dépôts) — ne cochez aucune case (pas de
   README, pas de .gitignore).
2. Dans le Cloud Shell, déposez le fichier `je-livre-mobile.zip` (menu ⋮ →
   Upload), puis :
   ```
   unzip je-livre-mobile.zip -d je-livre-mobile
   cd je-livre-mobile
   git init
   git add .
   git commit -m "Premier envoi"
   git branch -M main
   git remote add origin https://github.com/VOTRE-NOM/je-livre-mobile.git
   git push -u origin main
   ```
   (remplacez VOTRE-NOM par votre nom d'utilisateur GitHub)

## Récupérer l'APK compilé

1. Sur GitHub, dans le dépôt `je-livre-mobile`, cliquez sur l'onglet
   **Actions**. Une compilation démarre automatiquement après le push
   précédent — comptez 5 à 10 minutes.
2. Une fois terminé (coche verte ✓), cliquez sur la compilation, puis tout en
   bas de la page sur **je-livre-debug-apk** pour le télécharger (un .zip
   contenant l'APK).
3. Transférez cet APK sur un téléphone Android (par exemple en vous l'envoyant
   par WhatsApp ou par e-mail) et installez-le directement — il faudra
   peut-être autoriser "Installer des apps inconnues" dans les réglages du
   téléphone, Android le proposera automatiquement au moment de l'installation.

## Mettre à jour l'app plus tard

Dès que je vous envoie un nouveau `index.html`, remplacez-le dans
`www/index.html` (toujours via l'upload dans le Cloud Shell), puis :
```
git add .
git commit -m "Mise à jour"
git push
```
GitHub recompile automatiquement une nouvelle version à chaque envoi.

## Avant de publier sur le Play Store (plus tard)

L'APK généré ici est une version de test, installable directement — très
utile pour essayer l'app dès maintenant. Pour publier sur le vrai Play Store,
il faudra une version *signée* (`.aab`), ce qui demande une clé de signature
à créer et conserver précieusement. On s'en occupera ensemble le moment venu
— ça aussi peut se faire entièrement depuis le Cloud Shell, pas besoin
d'Android Studio.
