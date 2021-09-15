## Setup der neuen Laptops

### Prüfen

* Ist MacOS vollständig installiert, d.h. ist der Desktop sichtbar?
* Besteht eine stabile Internetverbindung (es werden ggf. mehrere Gb an Daten transferiert!)

### Installationen

##### Install & Setup Git

* Install Homebrew `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
* Install Git: `brew install git`
  * Note: `echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/----------/.zprofile`
  * Note: `eval "$(/opt/homebrew/bin/brew shellenv)"`
* Install GCM Core: `brew tap microsoft/git` und `brew install --cask git-credential-manager-core`
* Install GitHub Extensions: `brew install gh`
* Configure Git: `gh auth login`

##### Prüfung der Installation

_Personal Access Token Variante_

1. Personal Access Token unter https://github.com/settings/tokens erstellen
2. Im Terminal: `git clone https://github.com/WildCodeSchool/sea-resources.git`
3. Datei `sandbox.txt` ändern
4. Änderungen pushen: `git add`, `git commit` und `git push`

_SSH Authentication Variante_

1. [SSH Keys erstellen](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
2. [SSH Public Key in GitHub hinterlegen](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) 
2. Im Terminal: `git remote set-url origin git@github.com:WildCodeSchool/sea-resources.git`
3. Datei `sandbox.txt` ändern
4. Änderungen pushen: `git add`, `git commit` und `git push`

#### Java Installation

* [Eclipse Temurin](https://adoptium.net/) - Java 11

##### Prüfung der Installation

_Neustart nach Installation ist erforderlich_

* Kann der Befehl `java -version` aufgerufen werden?
* Kann der Befehl `javac -version` aufgerufen werden?

#### Allgemeiner Editor 

* [Visual Studio Code](https://code.visualstudio.com/)

_Note: Associate all text file types with VSCode_

##### Prüfung der Installation

* Ist eine Desktopverknüpfung vorhanden?
* Kann `code` in einem Terminal aufgerufen werden?

#### Java IDE 

* [IntelliJ IDEA Community Ed. for Mac](https://www.jetbrains.com/idea/download/#section=mac)

_Note: Associate Java, Kotlin and Groovy files with IntelliJ_  
