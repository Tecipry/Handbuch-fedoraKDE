^#ToDo 

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

