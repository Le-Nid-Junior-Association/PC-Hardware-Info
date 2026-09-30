## Comment utiliser le programme

Il y a deux façons de l'utiliser :

### Option 1 — Télécharger le .exe et l'exécuter (sans rien installer)

1. Télécharge `PC-Hardware-Info.exe` depuis ce dépôt (ou depuis le zip).
2. Mets-le dans un dossier de ton choix (par exemple le bureau).
3. Double-clique dessus (ou tape `PC-Hardware-Info.exe` dans une invite de commandes).

C'est tout : pas besoin de compiler, installer Visual Studio, ou quoi que ce soit d'autre.

📌 Quand tu génères le rapport (option 7), le dossier `reports/` se crée tout seul à côté du .exe.

### Option 2 — Télécharger le code source et le compiler

1. Télécharge le zip (ou « Clone » le dépôt).
2. Extrais-le dans un dossier.
3. Compile-le (commandes ci-dessous).
4. Lance le programme généré.

### Comment compiler

Windows — Visual Studio :

Ouvre « x64 Native Tools Command Prompt for Visual Studio », va dans le dossier du projet, puis :

cd /d C:\chemin\vers\ton\dossier\PC-Hardware-Info
cl /EHsc src\*.cpp advapi32.lib /FePC-Hardware-Info.exe

Windows — MinGW, ou Linux :

g++ -std=c++11 -Wall -Wextra -o PC-Hardware-Info src/main.cpp src/CPU.cpp src/RAM.cpp src/Storage.cpp src/GPU.cpp src/System.cpp src/Report.cpp

CMake (Windows, Linux, macOS) :

cmake -B build -S .
cmake --build build