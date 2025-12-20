#ToDo 

---
# Geschichte

Was ist "Das Terminal" eigentlich? Der Begriff stammt schon aus der frühen Geschichte des Computers. Damals war es eine große Herausforderung, mit dem System zu interagieren. Man hat ganze Räume welche mit einer riesigen Maschine gefüllt sind und irgendwie muss man nun Informationen in diese Maschine hinein- und herausbekommen.

Hierfür wurde eine Schnittstelle zur Maschine geschaffen, über welche entweder von der Maschine Daten ausgegeben werden konnten, oder Daten in die Maschine hinein gegeben werden konnten. Praktisch gesehen ist dies also einfach ein Datenkabel. Und am anderen Ende von diesem Kabel befand sich das Terminal. Hierbei handelte es sich oft um einen einfachen Bildschirm zum anzeigen von Textzeilen und eine Tastatur. Daten welche vom Computer kamen wurden auf dem Bildschirm angezeigt und über die Tastatur konnten Daten an den Computer geschickt werden. 

Historisch gesehen ist das Terminal also gar kein Teil des eigentlichen Computers, sondern nur eine 

---
# Befehlsübersicht

---
## Allgemein

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
flatpak update #sudo ist aufgrund der isolierten flatpak Pakete nicht nötig
```

- Aktualisiert alle installierten Pakete auf die neueste Version

### `remove`

```sh
sudo dnf remove <package-name>
flatpak uninstall <package-name>
```

- Deinstalliert ein Paket und seine Abhängigkeiten

