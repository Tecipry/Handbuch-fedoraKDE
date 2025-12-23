
---
# Geschichte

Was ist "Das Terminal" eigentlich? Der Begriff stammt schon aus der frühen Geschichte des Computers. Damals war es eine große Herausforderung, mit dem System zu interagieren. Man hatte ganze Räume, gefüllt mit riesigen Maschinen, und irgendwie muss man nun Informationen in diese Maschine hinein- und herausbekommen.

Hierfür wurde eine Schnittstelle zur Maschine geschaffen, über welche entweder von der Maschine Daten ausgegeben werden konnten, oder Daten in die Maschine hinein gegeben werden konnten. Praktisch gesehen ist dies also einfach ein Datenkabel. Und am anderen Ende von diesem Kabel befand sich das Terminal. Hierbei handelte es sich oft um einen einfachen Bildschirm zum anzeigen von Textzeilen und eine Tastatur. Daten welche vom Computer kamen wurden auf dem Bildschirm angezeigt und über die Tastatur konnten Daten an den Computer geschickt werden. 

Historisch gesehen ist das Terminal also gar kein Teil des eigentlichen Computers, sondern nur ein angeschlossenes Gerät um mit diesem zu interagieren, wie eine Maus oder ein Drucker.

---
# Grundprinzipien

Beim öffnen des Terminals sehen wir folgendes:
![](99%20assets/Pasted%20image%2020251220133111.png)
Hieraus können wir drei Dinge ablesen:

1. `tristan` ist der Nutzer welcher gerade das Terminal nutzt
2. `fedora` ist der Name des Rechners
3. `~` ist der Pfad im Dateisystem an dem wir uns gerade befinden. Die Tilde (`~`) ist dabei ein spezielles Zeichen für das `Home` Verzeichnis des Nutzers. Der eigentliche Pfad lautet hier also `/home/tristan`.

Alles was im Terminal geschieht, wird an einem bestimmten Ort im Dateisystem gemacht. Man spricht auch vom "working directory", also der Pfad bei welchem gerade gearbeitet wird. Dies ist natürlich vor allem relevant wenn wir mit Dateien arbeiten. Bevor wir dazu kommen, sollten wir uns jedoch kurz anschauen wie wir im Dateisystem navigieren können.

---
## Pfade im Dateisystem

Fangen wir an, indem wir uns kurz anschauen was mit einem "Pfad" gemeint ist. Grundsätzlich beschreibt ein Pfad immer einen Weg, in zu einem Ort im Dateisystem. Hierbei können wir zwischen zwei Arten unterscheiden:

1. **absoluter Pfad**
	Ein absoluter Pfad beginnt immer im Ursprung des Dateisystems. Unter Windows ist dies in den meisten Fällen `C:`. Unter Linux ist das immer `/`. Der absolute Pfad zum `Documents` Ordner des Benutzers "admin" lautet: `/home/admin/Documents/`.
2. **relativer Pfad**
	Ein relativer Pfad beginnt an der aktuellen Position und beschreibt den Weg von diesem Punkt aus. Wenn wir uns also im Nutzerordner von admin befinden (also in `/home/admin/`), dann lautet der relative Pfad zum `Documents` Ordner `Documents/`. Oft beginnen relative Pfade auch mit `./`. Auf die Bedeutung hiervon gehe ich ein paar Absätze weiter unten nochmal ein.

Das Ziel eines Pfades kann dabei entweder ein Ordner (z.B. `/home/admin/Documents/`) oder eine Datei (z.B. `/home/admin/Documents/wichtigesDokument.txt`) sein. Ordner- und Dateinamen in einem Pfad sind case-sensitive. Das bedeutet: `Documents` und `documents` sind zwei unterschiedliche Ordner. Dementsprechend muss hier auf die richtige Schreibweise geachtet werden. Mit `tab` können die Namen auch vervollständigt werden

---
## Navigation

Um navigieren zu können, müssen wir natürlich erstmal wissen welche Dateien existieren. Hierfür wird der Befehl `ls` genutzt, welcher für "list" steht. In den folgenden Beispielen ist immer in der ersten Zeile der ausgeführte Befehl und ggf. in den darauffolgenden Zeilen die Ausgabe zu sehen. Am besten probierst du die Befehle auch selber aus.

```sh
ls  
Applications  Desktop      Documents  Music     Public     Templates  
bin           Development  Downloads  Pictures  Scripting  Videos
```

Ein Befehl besteht immer aus dem Namen und zugehörigen Parametern. Eigentlich sind Parameter nicht optional, doch unter Umständen existieren Standardwerte welche genutzt werden, wenn wir nichts eingeben. In  das working directory, also der Pfad an dem wir uns gerade befinden, der Standardwert. Wir können allerdings auch andere Pfade als Parameter mitgeben, um zum Beispiel den Inhalt des Ordners `Documents` zu sehen:

```sh
ls Documents/
```

Apropros working directory. Auch wenn wir dieses, wie oben beschrieben, sehr leicht ablesen können, existiert natürlich ein Befehl um es anzuzeigen. Dieser lautet "print working directory", oder kurz `pwd`.

```sh
pwd
/home/tristan
```

Lass uns in den `Documents` Ordner hinein navigieren. Hierfür nutzen wir den Befehl `cd`, welcher für "change directory" steht.

```sh
cd Documents/
```

Wir sehen, dass wir uns an einem neuen Ort im Dateisystem befinden:
![](99%20assets/Pasted%20image%2020251220142146.png)

Wir haben eben schon mit dem `ls` Befehl festgestellt, dass dieser Ordner leer ist. Dies stimmt allerdings nicht ganz, den standardmäßig zeigt uns der `ls` Befehl keine versteckten Dateien, Hierfür müssen wir eine sogenannte Flag nutzen. Flags sind ähnlich wie Optionen, bloß dass sie optional sind. Über die Flag `-a` (für "all") können wir die versteckten Dateien in unserem `Documents` Ordner sehen.

```sh
ls -a  
.  ..
```

Das ist ein komischer Ergebnis. Was ist `.` und `..`? 

Hier kommen wir zurück zu einem Konzept, welches ich am Anfang des Handbuches bereits kurz angesprochen hatte: [Alles ist eine Datei](Der%20grobe%20Aufbau%20deines%20Systems.md#Alles%20ist%20eine%20Datei). Und diese beiden Dateien sind für die Navigation wichtig: 

- `.` beschreibt das aktuelle Verzeichnis und ist somit für relative Pfade sehr praktisch. In den vorherigen Beispielen habe ich ja bereits relative Pfade genutzt, z.B. mit `Documents/`. Wenn wir dies expliziter als relativen Pfad angeben wollen, können wir auch `./Documents/` schreiben. In unseren Beispielen macht dies allerdings keinen Unterschied.
- `..` beschreibt das überliegende Verzeichnis, das sogenannte "parent directory". Wir brauchen es also, um einen Pfad zum überliegenden Ordner zu erstellen zu können.

Navigiere zurück in dein Home Verzeichnis, also einen Ordner "nach oben".

```sh
cd ..
```


---
## Ordner und Dateien

Jetzt können wir anfangen, mit Ordnern und Dateien zu arbeiten. Zum erstellen eines Ordners wird der Befehl `mkdir` genutzt, welcher für "make directory" steht. Erstelle einen Ordner in `Documents` damit wir dort ein wenig testen können.

```sh
mkdir ./Documents/einNeuerOrdner/
```

Nutze den `cd` Befehl, um in den eben erstellten Ordner zu navigieren.

>[!TIP]- Lösung
> ```sh
> cd ./Documents/einNeuerOrdner/
> ```
> 
---


> [!NOTE] Hinweis
> Am Ende dieses Abschnitts habe ich alle beschriebenen (und auch einige nicht beschriebene) Befehle gesammelt: [Befehlsübersicht](Das%20Terminal.md#Befehlsübersicht).

Lass uns als nächstes eine Datei erstellen. Hierfür wird der Befehl `touch` genutzt.
```sh
touch datei.txt
```

Hierbei müssen wir darauf achten, auch die Dateiendung mit anzugeben. Ansonsten haben wir eine Datei ohne Dateityp.

Zum bearbeiten der Datei können wir den Editor `nano` nutzen. Dies ist ein minimalistischer Texteditor welcher direkt im Terminal funktioniert.
```sh
nano datei.txt
```

> [!NOTE] Hinweis
> Wir hätten übrigens auch direkt `nano datei.txt` nutzen können. Wenn wir hier einen Pfad angeben welcher nicht existiert, dann erstellt nano diese Datei für uns.

Nun können wir die Datei bearbeiten. Schreibe zum Beispiel "Hallo Welt!" in die erste Zeile. Am unteren Rand sehen wir einige Menüoptionen von nano. Diese werden durch Tastenkürzel genutzt. 
![](99%20assets/Pasted%20image%2020251220144939.png)

Um zu speichern müssen wir die Option `Write Out` aktivieren. Dies tuen wir mit `strg + o`. Anschließend bestätigen wir mit `Enter`. Um dann nano zu verlassen nutzen wir `strg + x` für `Exit`.

Nun haben wir eine Datei mit Inhalt. Um diesen Inhalt anzuzeigen, können wir natürlich einen Editor (wie nano) nutzen. Wenn aber nur kurz einen Blick auf den Inhalt werden möchte, ist der `cat` Befehl einfacher. Dies steht für "concatinate", weil der Inhalt der Datei quasi an den Output des Terminals "angehängt" wird.

```sh
cat datei.txt
```

> [!TIP]- Exkurs: Output
> Tatsächlich gibt es mehrere "Outputs", sogenannte Streams, für verschiedene Zwecke. Eine Information des Systems kann über verschiedene Streams ausgegeben werden. So gibt es z.B. `stdout` ("standard out"), welchem wir gerade folgen - und dem man eigentlich immer folgt. Es gibt aber z.B. auch `stderr` ("standard error"), welcher speziell für Fehlermeldungen genutzt wird.
> 
> Denk zurück an die historische Entstehung des Terminals als Ein- und Ausgabegerät. Ein anderer Stream ist wie ein anderes Kabel welches wir an unser Terminal hängen. Und die Maschine gibt an diesem anderen Kabel eben andere Informationen aus.

Nun ist natürlich noch interessant, wie wir diese Datei wieder löschen können. Hierfür wird der `rm` Befehl genutzt, welcher für "remove" steht.

```sh
rm datei.txt
```

Mit `rm` lassen sich auch Ordner löschen. Hierfür muss die Flag `-r` ("recursive") genutzt werden. Navigiere zurück in den Documents Ordner und lösche das Verzeichnis `einNeuerOrdner`.

> [!TIP]- Lösung
> ```sh
> cd ..
> rm einNeuerOrdner/
> ```

Mit dem `ls` Befehl können wir nun sehen, dass unser Documents Ordner nun wieder leer ist.
```sh
ls
# (leere Ausgabe)
```

Nun ist unser Terminal stark zugemüllt mit dem ganzen Text unserer Befehle. Mit dem Befehl `clear` kannst du hier ein wenig aufräumen.

```sh
clear
```


---
# Befehlsübersicht

---
## Navigation und Dateien

### `ls`

```sh
ls <Verzeichnis>
```

> `-a`: zeigt auch versteckte Dateien
> `-l`: zeigt zusätzliche Infos wie Besitzer der Datei

- "list"
- listet den Inhalt des angegebenen Verzeichnisses auf

### `cd`

```sh
cd <Verzeichnis>
```

- "change directory"
- ändert das working directory zum angegeben Verzeichnis

### `pwd`

```sh
pwd
```

- "print working directory"

### `mkdir`

```sh
mkdir <Verzeichnisname>
```

> `-p`: "parents" -> Wenn mehrere Ordner im Pfad nicht existieren

- "make directory"
- erstellt einen Ordner

### `touch`

```sh
touch <Dateiname>
```

- erstellt eine Datei

### `cat`

```sh
cat <Dateiname>
```

- "concatinate"
- schreibt den Inhalt einer Datei zu stdout

### `rm`

```sh
rm <Pfad>
```

> `-r`: "recursive"  -> für Verzeichnisse

- "remove"
- Löscht eine Datei

---
## Paketmanager

Befehle für die Arbeit mit den Paketmanagern `dnf` und `flatpak`. Weitere Infos zum Paketmanager finden sich im Abschnitt [Die Installation von Apps](Die%20Installation%20von%20Apps.md).

Die Überschriften sind immer mit dem "dnf Namen" betitelt, falls der äquivalente Flatpak Befehl abweichen sollte.

Für viele dnf Befehle ist `sudo` nötig. Da flatpaks stark vom restlichen System isoliert sind, ist hier die erhöhten Rechte meist nicht notwendig.

### `install`

```sh
sudo dnf install <package-name>
flatpak install <package-name>
```
- Installiert ein Paket und seine Abhängigkeiten

### `upgrade`

```sh
sudo dnf upgrade
flatpak update
```

- Aktualisiert alle installierten Pakete auf die neueste Version

### `remove`

```sh
sudo dnf remove <package-name>
flatpak uninstall <package-name>
```

- Deinstalliert ein Paket und seine Abhängigkeiten

