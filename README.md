

In diesem Guide versuche ich, einen Einstieg in die Linux Welt zu ermöglichen. Da dieser primär für meine wunderbare Partnerin geschrieben ist, beziehe ich mich dabei auf die Distro welche auf ihrem Rechner landen wird: Fedora KDE. 
An einigen Stellen in diesem Guide sind Hyperlinks zu finden. Wenn solch ein Link direkt auf einem Wort hinterlegt ist wie [hier](Handbuch-fedoraKDE/README.md#Übersicht), so verlinkt dieser an eine andere Stelle im Guide. Wenn er sich in einer Klammer hinter dem Wort befindet, ist es ein weiterführender Link der aus diesem Guide herausführt, wie hier ([youtube](https://www.youtube.com/watch?v=dQw4w9WgXcQ)).

---
# Übersicht

Ist der Rechner an? Wunderbar. 
Du fängst am besten an, indem du selber experimentierst. Versuche eine Datei zu erstellen, schau dir an was du im Dateisystem findest, probier dich in den Einstellungen herum, oder schau wie du eine App installieren kannst. Am besten lernt es sich beim probieren, also sei mutig und probier die Dinge einfach Mal aus. Und wenn du das gemacht hast, kannst du hierher zurückkommen.

---
## Der grobe Aufbau deines Systems

---
### Was ist "Linux"?

Wenn man von "Linux" redet, hat man oft ein gesamtes Betriebssystem im Kopf, ähnlich wie wenn man von "Windows" redet. Das trifft hier aber nicht zu. "Linux" ist eigentlich nur der Name für den zentralsten Teil des Betriebssystems: Den sogenannten "Kernel" ([wikipedia](https://de.wikipedia.org/wiki/Kernel_(Betriebssystem))). Um ein komplettes Betriebssystem zu bekommen, benötigt man noch viele weitere Teile, z.B. einen Paketmanager, verschiedene Systemdienste ("Daemons") oder eine Desktop-Umgebung. Eine Zusammenstellung von all diesen Dingen zu einem funktionierenden Betriebssystem wird "Linux-Distribution" ([wikipedia](https://de.wikipedia.org/wiki/Linux-Distribution)) genannt - oder kurz oft einfach nur "Distro".

Und das ist Fedora KDE, dein aktuelles Betriebssystem, auch. Eine Zusammenstellung von verschiedensten Programmen mit dem Linux-Kernel im Zentrum.

---
### Einige Begrifflichkeiten

Ähnlich wie "Linux" eigentlich nicht das gesamte Betriebssystem beschreibt, gibt es viele Begriffe auf die man früher oder später stößt, bei denen es praktisch sein kann etwas mehr Kontext zu haben. Dies ist definitiv keine vollständige Liste sondern mehr eine Sammlung von Dingen, die mir beim schreiben und aus meiner eigenen Erfahrung aufgefallen sind.

#### `Kernel`
Der Kern eines Betriebssystems, der die grundlegendsten Funktionen übernimmt welche nötig sind, damit der Computer überhaupt irgendetwas machen kann
#### `Distro`
Kurz für "Distribution", oft auch "Linux-Distro" oder ähnliches.
Eine Distro eine Auswahl aufeinander abgestimmter Softwarepakete mit dem Linux-Kernel im Zentrum. Viele Distros lassen sich in "Familien" einordnen, da sie aufeinander basieren oder ähnliche Software nutzen. Mehr Infos auf Wikipedia ([wikipedia](https://de.wikipedia.org/wiki/Linux-Distribution)).
Bekannte Distros sind unter anderem:
- `Debian` 
	Auf debian basiert eine große Familie an weiteren Distros wie `ubuntu` (auf welchem wiederum dutzende Distros basieren), `Kali Linux` oder `Raspberry Pi OS`.
- `Linux Mint`
- `Fedora`
	Zu dieser Familie, entwickelt vom fedoraproject ([fedoraproject](https://www.fedoraproject.org/)), gehören Distros wie `Fedora Workstation`, `Fedora Server`, oder `Fedora KDE` - oder wenn wir ganz korrekt sein wollen: `Fedora KDE Plasma Desktop`.
	Auch `Red Hat Enterprise Linux` ist eine von der Firma RedHat ([redhat](https://www.redhat.com/de)) entwickelte Distro, welche sich an Geschäftskunden richtet und dabei auf Fedora basiert.
#### `Desktop-Umgebung` bzw. `Desktop-Environment`
Eine Sammlung an Paketen, durch welche eine grafische Benutzeroberfläche für das System ermöglicht wird. Hierzu gehören unter anderem meistens Dinge ein Fenstermanager, damit Apps entsprechend angezeigt werden können, Standardprogramme wie eine Office-Suite, oder eine Statusbar um Systeminformationen anzuzeigen ([reddit](https://www.reddit.com/r/linux4noobs/comments/f2ye9t/what_is_a_desktop_environment/)).
Bekannte Desktop-Umgebungen sind z.B. `Gnome` und `KDE Plasma` (oft kurz einfach nur `KDE`, auch wenn dies eigentlich etwas anderes ist: [reddit](https://www.reddit.com/r/linux4noobs/comments/v4iwb9/difference_between_kde_and_kde_plasma/)).

---
### Tipps bei Fragen und zur Fehleranalyse 

Früher oder später wirst du an einer bestimmten Sache mit diesem Guide und ein paar schnellen Suchen in den Systemeinstellungen nicht weiterkommen. Vielleicht willst du etwas bestimmtes einstellen, triffst auf einen komischen Fehler, oder möchtest einfach nur einen Begriff verstehen. Hierbei ist ganz wichtig: Google ist dein Freund! Warte, lass mich daraus eine Überschrift machen um später immer wieder hierher verlinken zu können :D

#### Google ist dein Freund

Linux wird von einem haufen Nerds entwickelt und genutzt. Das führt dazu, dass zu den allermeisten Dingen schon irgendetwas geschrieben wurde, irgendwer in einem Forum eine entsprechende Frage gestellt hat, oder die Antwort in der entsprechenden Dokumentation liegt. Oft reicht es deswegen, in der Suchmaschine des Vertrauens ein paar entsprechende Stichworte einzugeben. Infos wie die [Desktop-Umgebung](Handbuch-fedoraKDE/README.md#Desktop-Umgebung%20bzw.%20Desktop-Environment), also bei dir "KDE Plasma" oder die [Distro](Handbuch-fedoraKDE/README.md#Distro), also "Fedora", sind hier oft sehr hilfreich. Da es so viele verschiedene Linux-Distros gibt, reicht es in der Regel nicht aus einfach nur Dinge wie "Linux" anzuhängen.
Mit ein paar guten Stichworten landet man dann tatsächlich in den allermeisten Fällen bei sehr hilfreichen Links - und nicht einfach nur bei einer generischen Microsoft help Seite, welche dir falsche Hoffnungen macht 😒.

In vielen Fällen ist auch Reddit sehr hilfreich. Subreddits wie r/Linux4Noobs ([reddit](https://www.reddit.com/r/linux4noobs/)) sind oft sehr praktisch um Konzepte oder Begriffe zu verstehen. Auch in diesem Guide finden sich bereits ein paar Links dorthin.
Nach meiner Erfahrung eignen sich KI Modelle wie ChatGPT, Perplexity, oder Claude eher schlecht zum lösen von Problemen. Zumindest wenn es darum geht tatsächlich ein Problem zu lösen, eine Einstellung zu finden oder etwas bestimmtes zu konfigurieren.

> [!TIP]- Exkurs: Befehle im Terminal
> 
> Es ist absolut verständlich, dass man als Anfänger versucht das Terminal zu meiden. Dies ist mit einer modernen Desktop-Umgebung für einen durchschnittlichen Nutzer auch sehr gut möglich. Oft findet man online allerdings trotzdem Terminal-Befehle als Antwort auf ein Problem. Und dies hat gute Gründe, denn das Terminal ist deutlich mächtiger als die grafische Oberfläche und viele Dinge können hier deutlich einfacher vorgenommen werden, wenn man weiß wie es funktioniert. 
> 
> > [!CAUTION] Im Terminal ist vor allem wichtig:
> > 
> > Führe einen Befehl immernur dann aus, wenn du verstehst was dieser macht. Auch hier helfen dir Ressourcen wie Google oder die Dokumentation. Und auch KI-Modelle sind hier oft sehr praktisch, wenn man diese darum bittet den Befehl entsprechend zu erklären. 
> 
> Ich werde in einem späteren Kapitel nochmal genauer auf einige Grundlagen zum Terminal eingehen - auch wenn sich dies nicht immer sonderlich Anfängerfreundlich anfühlt.

### Die Desktop-Umgebung "KDE Plasma"

Für die Arbeit mit dem Computer ist für uns die Desktop-Umgebung (oder englisch: "Desktop-Environment") sehr wichtig. Grundlegend gesagt kümmert sich die Desktop-Umgebung darum, dass Dinge am Ende auf dem Bildschirm zu sehen sind und du als Nutzer mit dem System auf grafische Weise interagieren kannst.

Für dich ist dies "KDE Plasma", welche oft auch einfach kurz als "KDE" bezeichnet wird, entwickelt von der [KDE-Community](https://kde.org/de/). Vielleicht sind dir in den vorinstallierten Apps schon einige Namen wie "KWrite", "KCalc", oder "KMail" aufgefallen. Diese stammen ebenfalls von denselben Entwicklern und sind als Teil der Distribution auf deinem System vorinstalliert.

Hier kommt übrigens auch das "KDE" im Namen von "Fedora KDE" her. Und hier liegt auch der Unterschied zu der anderen großen Fedora Distro "Fedora Workstation": Dort kommt nämlich die Desktop-Umgebung "Gnome" zum Einsatz.

# weitere Links

(callout types)

> [!NOTE]  
> Highlights information that users should take into account, even when skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]  
> Crucial information necessary for users to succeed.

> [!WARNING]  
> Critical content demanding immediate user attention due to potential risks.

> [!CAUTION]
> Negative potential consequences of an action.