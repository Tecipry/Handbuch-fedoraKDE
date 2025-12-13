Ähnlich wie "Linux" eigentlich nicht das gesamte Betriebssystem beschreibt, gibt es viele Begriffe auf die man früher oder später stößt, bei denen es praktisch sein kann etwas mehr Kontext zu haben. Dies ist definitiv keine vollständige Liste sondern mehr eine Sammlung von Dingen, die mir beim schreiben und aus meiner eigenen Erfahrung aufgefallen sind.

---
## `Kernel`

Der Kern eines Betriebssystems, der die grundlegendsten Funktionen übernimmt welche nötig sind, damit der Computer überhaupt irgendetwas machen kann

---
## `Distro`

Kurz für "Distribution", oft auch "Linux-Distro" oder ähnliches.
Eine Distro eine Auswahl aufeinander abgestimmter Softwarepakete mit dem Linux-Kernel im Zentrum. Viele Distros lassen sich in "Familien" einordnen, da sie aufeinander basieren oder ähnliche Software nutzen. Mehr Infos auf Wikipedia ([wikipedia](https://de.wikipedia.org/wiki/Linux-Distribution)).
Bekannte Distros sind unter anderem:
- `Debian` 
	Auf Debian basiert eine große Familie an weiteren Distros wie `ubuntu` (auf welchem wiederum dutzende Distros basieren), `Kali Linux` oder `Raspberry Pi OS`.
- `Linux Mint`
- `Fedora`
	Zu dieser Familie, entwickelt vom fedoraproject ([fedoraproject](https://www.fedoraproject.org/)), gehören Distros wie `Fedora Workstation`, `Fedora Server`, oder `Fedora KDE` - oder wenn wir ganz korrekt sein wollen: `Fedora KDE Plasma Desktop`.
	Auch `Red Hat Enterprise Linux` ist eine von der Firma RedHat ([redhat](https://www.redhat.com/de)) entwickelte Distro, welche sich an Geschäftskunden richtet und dabei auf Fedora basiert.

---
## `Desktop-Umgebung` bzw. `Desktop-Environment`

Eine Sammlung an Paketen, durch welche eine grafische Benutzeroberfläche für das System ermöglicht wird. Hierzu gehören unter anderem meistens Dinge ein Fenstermanager, damit Apps entsprechend angezeigt werden können, Standardprogramme wie eine Office-Suite, oder eine Status-bar um Systeminformationen anzuzeigen ([reddit](https://www.reddit.com/r/linux4noobs/comments/f2ye9t/what_is_a_desktop_environment/)).
Bekannte Desktop-Umgebungen sind z.B. `Gnome` und `KDE Plasma` (oft kurz einfach nur `KDE`, auch wenn dies eigentlich etwas anderes ist: [reddit](https://www.reddit.com/r/linux4noobs/comments/v4iwb9/difference_between_kde_and_kde_plasma/)).

---

## `Paket` bzw. `package`

Vereinfach eine Anwendung, also eine App für das Gerät. Dazu gehören allerdings nicht nur Dinge, die der Nutzer selber installiert. Auch Dinge die das System braucht um zu funktionieren sind Pakete.

---
## `Paketmanager` bzw. `package manager`

Ein Paketmanager kümmert sich um installierte Pakete auf dem System. Dazu gehören offensichtliche Aufgaben wie die Installation oder das Updaten. Allerdings auch deutlich komplexere Themen wie das automatische managen von Abhängigkeiten. So gibt es eine zentrale Stelle - den Paketmanager - um sich um alle installierten Dinge zu kümmern.

Auf verschiedenen Distros werden standardmäßig unterschiedliche Paketmanager genutzt. Dies sind zum Beispiel:
- `dnf` in der Fedora Familie
- `apt` in der Debian Familie

Natürlich kann der Paketmanager auf einem System geändert werden - und genauso ist es auch möglich mehrere Paketmanager parallel zu nutzen. Einer der großen Vorteile, nämlich zentralisiertes Management von Anwendungen und deren Abhängigkeiten, geht hierdurch jedoch verloren. Deshalb sollte dies tendenziell vermieden werden. Natürlich gibt es auch hierzu Ausnahmen. Genaueres ist im Kapitel [Wie installiere ich Apps?](Wie%20installiere%20ich%20Apps?.md) zu finden.