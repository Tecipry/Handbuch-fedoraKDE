
---
## Was ist "Linux"?

Wenn man von "Linux" redet, hat man oft ein gesamtes Betriebssystem im Kopf, ähnlich wie wenn man von "Windows" redet. Das trifft hier aber nicht zu. "Linux" ist eigentlich nur der Name für den zentralsten Teil des Betriebssystems: Den sogenannten "Kernel" ([wikipedia](https://de.wikipedia.org/wiki/Kernel_(Betriebssystem))). Um ein komplettes Betriebssystem zu bekommen, benötigt man noch viele weitere Teile, z.B. einen Paketmanager, verschiedene Systemdienste ("Daemons") oder eine Desktop-Umgebung. Eine Zusammenstellung von all diesen Dingen zu einem funktionierenden Betriebssystem wird "Linux-Distribution" ([wikipedia](https://de.wikipedia.org/wiki/Linux-Distribution)) genannt - oder kurz oft einfach nur "Distro".

Und das ist Fedora KDE, dein aktuelles Betriebssystem, auch. Eine Zusammenstellung von verschiedensten Programmen mit dem Linux-Kernel im Zentrum.

---
## Die Desktop-Umgebung "KDE Plasma"

Für die Arbeit mit dem Computer ist für uns die Desktop-Umgebung (oder englisch: "Desktop-Environment") sehr wichtig. Grundlegend gesagt kümmert sich die Desktop-Umgebung darum, dass Dinge am Ende auf dem Bildschirm zu sehen sind und du als Nutzer mit dem System auf grafische Weise interagieren kannst.

Für dich ist dies "KDE Plasma", welches oft auch einfach kurz als "KDE" bezeichnet wird, entwickelt von der [KDE-Community](https://kde.org/de/). Vielleicht sind dir in den vorinstallierten Apps schon einige Namen wie "KWrite", "KCalc", oder "KMail" aufgefallen. Diese stammen ebenfalls von denselben Entwicklern und sind als Teil der Distribution auf deinem System vorinstalliert.

Hier kommt übrigens auch das "KDE" im Namen von "Fedora KDE" her. Und hier liegt auch der Unterschied zu der anderen großen Fedora Distro "Fedora Workstation": Dort kommt nämlich die Desktop-Umgebung "Gnome" zum Einsatz.

---

## Alles ist eine Datei

Ein sehr wichtiger Grundbaustein von Linux lautet: **Alles ist eine Datei**.
Und das ist wirklich wörtlich so gemeint. Alles was wir auf dem System machen, alles was irgendwie geschieht. Vom offensichtlichen, wie den `.txt` Dateien die du selber angelegt hast, über den Code welcher das Betriebssystem laufen lässt, bis zu den Eingaben die ich gerade auf meiner Tastatur mache: Alles ist eine Datei.

>[!TIP]- Exkurs: Eingaben
> Öffne deinen Dateiexplorer und navigiere in den Ordner `/dev/input/`. Hier siehst du verschiedene event Dateien, mit welchen die Eingabe von Daten durch angeschlossene Hardware geschieht. 
> ![](99%20assets/Pasted%20image%2020251220134220.png)
> 
> Wenn ich eine Taste auf meiner Tastatur drücke oder die Maus bewege, ändert sich hier eine Datei und das Betriebssystem kann darauf basierend die eingegebenen Daten weiter verarbeiten.

Für die alltägliche Arbeit ist es natürlich nicht sonderlich interessant wie die Dinge im Hintergrund geschehen. An einigen Stellen in diesem Handbuch wird dieses Wissen aber beim Verständnis helfen. Vor allem wenn wir später zu technischeren Themen wie [dem Terminal](Das%20Terminal.md) kommen.