## Setup der neuen Laptops

### Prüfen

* Ist Windows 10 installiert?
* Gibt es keine Restriktionen bgzl. Installationen (Adminrechte)?

### Installationen

#### Lokale Git-Installation

* [GitHub Desktop](https://desktop.github.com/)

##### Setup Git

* Credentials aus GitHub nutzen

##### Prüfung der Installation

_Personal Access Token Variante_

1. Personal Access Token unter https://github.com/settings/tokens erstellen
2. Im Terminal: `git clone https://github.com/WildCodeSchool/sea-resources.git`
3. Datei `sandbox.txt` ändern
4. Änderungen pushen: `git add`, `git commit` und `git push`

_SSH Authentication Variante_

1. [SSH Keys erstellen](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
2. Im Terminal: `git remote set-url origin git@github.com:WildCodeSchool/sea-resources.git`
3. Datei `sandbox.txt` ändern
4. Änderungen pushen: `git add`, `git commit` und `git push`

#### Java Installation

* [Eclipse Temurin](https://adoptium.net/) - Java 11

#### Allgemeiner Editor 

* [Visual Studio Code](https://code.visualstudio.com/)

_Note: Associate all text file types with VSCode_

#### Java IDE 

* [IntelliJ IDEA Community Ed. for Windows](https://www.jetbrains.com/idea/download/#section=windows)

_Note: Associate Java, Kotlin and Groovy files with IntelliJ_  