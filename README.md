

In diesem Guide versuche ich, einen Einstieg in die Linux Welt zu ermöglichen. Da dieser primär für meine wunderbare Partnerin geschrieben ist, beziehe ich mich dabei auf die Distro welche auf ihrem Rechner landen wird: Fedora KDE. 
An einigen Stellen in diesem Guide sind Hyperlinks zu finden. Wenn solch ein Link direkt auf einem Wort hinterlegt ist wie [hier](Handbuch-fedoraKDE/README.md#Übersicht), so verlinkt dieser an eine andere Stelle im Guide. Wenn er sich in einer Klammer hinter dem Wort befindet, ist es ein weiterführender Link der aus diesem Guide herausführt, wie hier ([youtube](https://www.youtube.com/watch?v=dQw4w9WgXcQ)).

# Übersicht

Ist der Rechner an? Wunderbar. 
Du fängst am besten an, indem du selber experimentierst. Versuche eine Datei zu erstellen, schau dir an was du im Dateisystem findest, probier dich in den Einstellungen herum, oder schau wie du eine App installieren kannst. Am besten lernt es sich beim probieren, also sei mutig und probier die Dinge einfach Mal aus. Und wenn du das gemacht hast, kannst du hierher zurückkommen.

## Der grobe Aufbau deines Systems

### Was ist "Linux"?

Wenn man von "Linux" redet, hat man oft ein gesamtes Betriebssystem im Kopf, ähnlich wie wenn man von "windows" redet. Das trifft hier aber nicht zu. "Linux" ist nur der Name für den zentralsten Teil des Betriebssystems: Den sogenannten "Kernel" ([wikipedia](https://de.wikipedia.org/wiki/Kernel_(Betriebssystem))). Um ein komplettes Betriebssystem zu bekommen, benötigt man noch viele weitere Teile, z.B. einen Paketmanager, verschiedene Systemdienste ("Daemons") oder eine Desktop-Umgebung. Eine Zusammenstellung von all diesen Dingen zu einem funktionierenden Betriebssystem wird "Linux-Distribution" ([wikipedia](https://de.wikipedia.org/wiki/Linux-Distribution)) genannt - oder kurz oft einfach nur "Distro".

Und das ist Fedora KDE, dein aktuelles Betriebssystem, auch. Eine Zusammenstellung von verschiedensten Programmen mit dem Linux-Kernel im Zentrum.

### Einige Begrifflichkeiten

Ähnlich wie "Linux" eigentlich nicht das gesamte Betriebssystem beschreibt, gibt es viele Begriffe auf die man früher oder später stößt, bei denen es praktisch sein kann etwas mehr Kontext zu haben. Dies ist definitiv keine vollständige Liste sondern mehr eine Sammlung von Dingen, die mir beim schreiben und aus meiner eigenen Erfahrung aufgefallen sind.

- `Kernel`
	Der Kern eines Betriebssystems, der die grundlegendsten Funktionen übernimmt welche nötig sind, damit der Computer überhaupt irgendetwas machen kann
- `Distro`
	Kurz für "Distribution", oft auch "Linux-Distro" o.ä.
	Ist eine Auswahl aufeinander abgestimmter Softwarepakete mit dem Linux-Kernel im Zentrum. Viele Distros lassen sich in "Familien" einordnen, da sie aufeinander basieren oder ähnliche Software nutzen. Mehr Infos auf Wikipedia ([wikipedia](https://de.wikipedia.org/wiki/Linux-Distribution)).
	Bekannte Distros sind unter anderem:
	- `Debian` 
		Auf debian basiert eine große Familie an weiteren Distros wie `ubuntu` (auf welchem wiederum dutzende Distros basieren), `Kali Linux` oder `Raspberry Pi OS`.
	- `Linux Mint`
	- `Fedora`
		Zu dieser Familie, entwickelt vom fedoraproject ([fedoraproject](https://www.fedoraproject.org/)), gehören Distros wie `Fedora Workstation`, `Fedora Server`, oder `Fedora KDE` - oder wenn wir ganz korrekt sein wollen: `Fedora KDE Plasma Desktop`.
		Auch `Red Hat Enterprise Linux` ist eine von der Firma RedHat ([redhat](https://www.redhat.com/de)) entwickelte Distro, welche sich an Geschäftskunden richtet und dabei auf Fedora basiert.
- `Desktop-Umgebung` / `Desktop-Environment`
	Eine Sammlung an Paketen, durch welche eine grafische Benutzeroberfläche für das System ermöglicht wird. Hierzu gehören unter anderem meistens Dinge ein Fenstermanager, damit Apps entsprechend angezeigt werden können, Standardprogramme wie eine Office-Suite, oder eine Statusbar um Systeminformationen anzuzeigen ([reddit](https://www.reddit.com/r/linux4noobs/comments/f2ye9t/what_is_a_desktop_environment/)).
	Bekannte Desktop-Umgebungen sind z.B. `Gnome` und `KDE Plasma` (oft kurz einfach nur `KDE`, auch wenn dies eigentlich etwas anderes ist: [reddit](https://www.reddit.com/r/linux4noobs/comments/v4iwb9/difference_between_kde_and_kde_plasma/)).
	


### Die Desktop-Umgebung "KDE Plasma"

Für die Arbeit mit dem Computer ist für uns die Desktop-Umgebung (oder englisch: "Desktop-Environment") sehr wichtig. Grundlegend gesagt kümmert sich die Desktop-Umgebung darum, dass Dinge am Ende auf dem Bildschirm zu sehen sind und du als Nutzer mit dem System auf grafische Weise interagieren kannst.

Für dich ist dies "KDE Plasma", entwickelt von der [KDE-Community](https://kde.org/de/). Vielleicht sind dir in den vorinstallierten Apps schon einige Namen wie "KWrite", "KCalc", oder "KMail" aufgefallen. Diese stammen ebenfalls von denselben Entwicklern und sind als Teil der Distribution auf deinem System vorinstalliert.
# weitere Links