SYLORA DESKTOP 0.1.0 — PROJET WINDOWS
=====================================

CE QUE CONTIENT CETTE VERSION
- Une application de bureau Tauri 2 (fenêtre native Windows, sans onglets de navigateur).
- Une interface SYLORA avec navigation et menus.
- Writer : éditeur de texte, styles, police, taille, gras/italique/souligné, listes, annuler/rétablir, sauvegarde locale dans le stockage de l'application et impression/export PDF via le dialogue Windows.
- Calc : grille de cellules éditables et export CSV. Les formules et calculs automatiques ne sont pas encore implémentés.
- Impress : première diapositive éditable et aperçu diaporama. L'édition multi-diapositives n'est pas encore implémentée.

INSTALLATION / COMPILATION SUR WINDOWS 10 OU 11
1. Décompressez le ZIP dans un dossier normal (pas dans OneDrive si possible).
2. Installez Node.js LTS : https://nodejs.org
3. Installez Rust : https://rustup.rs
4. Installez Microsoft C++ Build Tools (charge de travail « Développement Desktop en C++ ») : https://visualstudio.microsoft.com/visual-cpp-build-tools/
5. Double-cliquez sur INSTALLER-WINDOWS.bat.
6. À la fin, l'installateur Windows sera dans src-tauri\target\release\bundle\nsis ou msi.

POURQUOI LE ZIP NE CONTIENT PAS DIRECTEMENT UN EXE ?
Le projet est préparé dans cet environnement Linux. La génération d'un installateur Windows doit être exécutée sur Windows avec les outils de compilation Windows installés. Le script ci-dessus automatise cette compilation sur votre PC.

LANCEMENT EN MODE DEVELOPPEMENT
Ouvrez PowerShell dans ce dossier, puis :
  npm install
  npm run tauri dev

NOTE
Ceci est une première base de bureau fonctionnelle, pas encore un remplacement complet de LibreOffice. Les fonctions avancées de Writer, les formules de Calc, les présentations multi-diapositives, l'ouverture native DOCX/XLSX/PPTX et la base de données seront développées ensuite.

METHODE PLUS SIMPLE : COMPILATION DANS LE CLOUD AVEC GITHUB
----------------------------------------------------------
Cette version contient un workflow GitHub Actions qui compile SYLORA sur un serveur Windows.
Vous n'avez donc PAS besoin d'installer Rust ou Visual Studio sur votre PC pour compiler.

Etapes :
1. Creez un depot GitHub vide (par exemple sylora-desktop).
2. Envoyez tous les fichiers et dossiers de ce projet dans le depot, y compris le dossier .github.
3. Ouvrez l'onglet Actions du depot GitHub.
4. Selectionnez "Build SYLORA for Windows" puis "Run workflow" si le lancement ne se fait pas automatiquement.
5. Attendez que le workflow soit termine avec une coche verte.
6. Ouvrez l'execution terminee et telechargez l'artefact "SYLORA-Windows-Installers".
7. Dans cet artefact, vous trouverez le programme d'installation .exe (NSIS) et/ou .msi.

IMPORTANT : GitHub compile le programme ; il ne l'installe pas automatiquement sur votre PC.
Le fichier .exe telecharge sera a lancer manuellement pour installer SYLORA.
