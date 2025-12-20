
Wenn du dein System schon etwas erkundet hast, wirst du wahrscheinlich auf das Software Centre gestoßen sein.

![](99%20assets/Pasted%20image%2020251213152023.png)

"Ich nutze also einfach diese App" wirst du dir denken. Und es spricht auch grundsätzlich nichts dagegen, deine Apps hier herunterzuladen und zu managen. Wenn du jedoch etwas tiefer in das Thema eintauchen willst, solltest du hier weiterlesen.

---
# Der Paketmanager

Wie der Name vermuten lässt, ist ein Paketmanager (oder englisch: package manager) dafür zuständig, Pakete auf dem System zu verwalten. Ein Paket kannst du dir vereinfacht als eine App vorstellen - auch wenn dies eigentlich nicht richtig ist. Mit einem Paketmanager werden Pakete (also quasi Apps) installiert, verwaltet, und gelöscht. 

Aber was bringt dir das? Lass uns einen Blick auf die Installation und anschließende Deinstallation einer App unter windows und unter Fedora mit dem Paketmanager `apt` werfen, um zu verstehen warum ein Paketmanager so unglaublich praktisch ist. Wir werden das ganze am Beispiel der App `OBS Studio` machen.

## Installation und Deinstallation einer App unter Windows

1. Beschaffung der Installationsdatei

	Zuerst benötigen wir unsere Installationsdatei. Hierzu suchen wir online zum Beispiel nach "OBS download" und stoßen auf die Website [obsproject.com](https://obsproject.com). Unter "Download" bekommen wir eine `.exe` Installationsdatei. Bei anderen Programmen könnte dies jedoch auch eine `.msi` Datei sein, oder etwas völlig anderes.

2. Der setup wizard
   
	Beim Ausführen der Installationsdatei startet der setup wizard. Nachdem wir uns durch das Menü geklickt haben, beginnt die eigentliche Installation. Im Hintergrund werden dabei hauptsächlich Dateien heruntergeladen und an verschiedenen Positionen im Dateisystem abgelegt.

2. Starten der App
   
	Nun ist die App installiert und kann normal gestartet werden. Für dieses Beispiel werden wir die App als nächstes allerdings wieder deinstallieren.

2. Deinstallation
   
	Wo fangen wir überhaupt hier an? 
	Der wahrscheinlich einfachste Weg beginnt in den Einstellungen: Unter "Apps" findet sich eine (mehr oder weniger vollständige) Liste der installierten Apps. Mit etwas Glück können wir hier die App auswählen und auf "Deinstallieren" drücken. Mit etwas Pech findet sich unsere App allerdings nicht in dieser Liste. 
	
	Da haben wir aber Glück, dass unser Betriebssystem eigentlich nur ein Skin für ältere Windows Versionen ist. Deshalb können wir über die Systemsteuerung zu den installierten Apps navigieren, um hier auf "Deinstallieren" zu drücken. Aber auch hier müssen wir hoffen, dass Microsoft uns wohlgesonnen ist - bei verschiedenen vorinstallierten Apps ist das ganze nämlich auch hier nicht möglich.

2. Der setup wizard, again
   
	Durch das drücken auf den "Deinstallieren" Knopf startet der setup wizard der App. Diesmal allerdings führt er uns durch den Deinstallationsprozess. Erneut können wir uns also durch die Menüs klicken, bis wir am Ende die App deinstalliert haben.

2. Aufräumen
   
	Oft werden bei der Deinstallation nicht alle Daten des Programms gelöscht. Zum Beispiel bleiben oft Konfigurationsdateien auf dem System zurück. Dies kann eine praktische Sache sein: Sollten wir das Programm zu einem späteren Zeitpunkt erneut installieren, können diese Dateien genutzt werden um unter anderem Einstellungen wieder herzustellen. Aber mal ernsthaft: Ist das wirklich nötig? Oft wird dadurch einfach nur unser System mit Müll gefüllt.
	
	Wenn wir diese Dateien also auch löschen wollen, beginnt eine manuelle Jagd. Und dafür müssen wir an wirklich einigen Stellen schauen. Hier nur eine Auswahl an Orten, an denen sich noch Dateien von unserem Programm finden könnten:
	
	```txt
	C:\Program Files\...
	C:\Program Files (x86)\...
	C:\ProgramData\...
	C:\Users\<USER>\AppData\Roaming\...
	C:\Users\<USER>\AppData\Local\...
	```
	
	Viel Spaß ;D

## Installation und Deinstallation einer App mit dem Paketmanager `apt`

1. Installation der App
   
	Öffne ein Terminal und führe dort folgenden Befehl aus:
	```sh
	sudo dnf install obs-studio
	```
	Da der Befehl mit `sudo` ausgeführt wird, müssen wir evtl. unser Passwort eingeben. 
	Kurz danach wird uns eine Liste angezeigt, welche wir durch das eingeben von `y` für `yes` sowie einem `Enter` bestätigen müssen.

1. Starten der App
   
	Die App kann nun normal gestartet und genutzt werden. Wie zuvor auch, werden wir die App im nächsten Schritt allerdings wieder deinstallieren.

1. Deinstallation der App
   
	Führe für die Deinstallation folgenden Befehl im Terminal aus:
	```sh
	sudo dnf remove obs-studio
	```
	Wieder wird uns eine Liste mit geplanten Änderungen angezeigt, welche wir mit `y` bestätigen können.

## Vergleich der beiden Abläufe

Was sind also die Vorteile die uns der Paketmanager in dieser Situation bringt. Auch wenn aus diesem Beispiele hoffentlich einige sehr offensichtliche Punkte ersichtlich sind, möchte ich diese, sowie auch einige weitere, hier einmal auflisten:
- Einfache Installation und Deinstallation
  
	Ich denke die vorherigen Kapitel belegen diese Aussage ausreichend.
	
- Einfache Updates
  
	Wenn wir Glück haben, können unsere Apps auf Windows sich selbst automatisch updaten. Wenn dies nicht der Fall ist, beginnt eine ähnliche Jagd wie schon bei der Installation, welche oft in einer kompletten Neuinstallation der App endet.
	Mit einem Paketmanager sind updates durch einen einzigen Befehl erledigt. In unserem Beispiel mit dnf lautet dieser:
	
	```sh
	sudo dnf upgrade
	```
	Dir fällt vielleicht auf, das hier kein bestimmtes Paket angegeben wird. Dieser Befehl updatet nämlich gleich alle Pakete, für die es ein update gibt - praktisch, oder?

- Besitzerverwaltung von Programmdateien
  
	Dir ist wahrscheinlich aufgefallen, dass es für die Deinstallation mit dem Paketmanager keinen "Aufräumen" - Schritt gibt. Der Grund dafür ist einfach: Er ist nicht nötig. Wenn ein Programm eine Konfigurationsdatei erstellt, dann weiß der Paketmanager zu welchem Programm diese Datei gehört. Somit können diese Dateien bei der Deinstallation ebenfalls gelöscht werden und es bleiben keine Reste zurück. Dies geschieht natürlich nicht mit Dateien welche mithilfe des Programms durch den Nutzer erstellt wurden: Die Aufnahmen die ich mit OBS gemacht habe, bleiben logischerweise auf dem System erhalten.

- Sichere Installation aus Vertrauenswürdiger Quelle
  
	Die Tatsache, dass wir auf Windows von irgendeiner Website eine Installationsdatei herunterladen müssen, stellt offensichtlicherweise ein Risiko dar. Es kommt oft vor, dass Hacker eine falsche Website für eine bekannte Software bauen, in der Hoffnung das Nutzer diese mit der echten Seite verwechseln und über den Download eine Schadsoftware installieren. Auch die Software aus unserem Beispiel, OBS, war in der Vergangenheit davon betroffen: [Google Ad serving fake OBS website with Malware | OBS Forums](https://obsproject.com/forum/threads/google-ad-serving-fake-obs-website-with-malware.162235/)
	
	Im Gegensatz dazu werden die Pakete, welche durch einen Paketmanager installiert werden können, zentral verwaltet. Hier werden die Pakete von vielen Augen überwacht und es kann sich nicht einfach ein falsches OBS einschleichen. Zusätzlich führt der Paketmanager während der Installation Sicherheitschecks durch, um sicherzustellen dass tatsächlich ein vertrauenswürdiges Paket aus einer vertrauenswürdigen Quelle installiert wird.

---
# Funktionsweise eines Paketmanagers

Woher weiß unser Paketmanager, welche App installiert werden soll wenn wir `obs-studio` eintippen? Hierfür ist beim Paketmanager ein "repository" hinterlegt. In diesem repository sind Informationen zu Apps hinterlegt, z.B.:
- Wie heißt die App?
- Eine Beschreibung der App
- Welche Versionen der App gibt es?
- Von wo kann ich die relevanten Dateien installieren?

Dieses repository wird an einem zentralen Ort gespeichert und gepflegt. Von dort kann sich der Paketmanager dann die aktuellsten Informationen zu den Apps besorgen. Auf diese Weise funktionieren dann auch App Updates: Im repository ist die neueste Version der App hinterlegt. Der Paketmanager erkennt, dass unsere installierte Version älter ist, und kümmert sich dann um das update sobald wir `sudo dnf upgrade` durchführen.

>[!TIP]- Exkurs: Repositorys
> Vielleicht ist dir schon ein Problem aufgefallen: Was passiert, wenn ich eine App installieren möchte die nicht im Repository meines Paketmanagers aufgelistet ist?
> 
> Es ist möglich, andere Repositorys zum Paketmanager hinzuzufügen, und somit Apps aus diesen anderen Repositorys zu installieren. Hier muss aber natürlich immer darauf geachtet werden, dass das Repository vertrauenswürdig ist. Öfters hat man den Fall, dass eine App nur mit bestimmten Paketmanagern installiert werden kann. In diesem Fall muss dann also ein anderer Paketmanager verwendet werden.
> 
> Wenn man nun einen anderen Paketmanager für die Installation von manchem Apps verwendet, verliert man natürlich teilweise einige der vorhin genannten Vorteile, da es nun nicht mehr eine zentrale Stelle zum managen Apps gibt.

Wenn wir also `sudo dnf install obs-studio` ausführen, sucht der Paketmanager in seinen repositorys nach einer Anwendung namens "obs-studio". Mit den Informationen aus dem Repository kann die App dann entsprechend installiert werden.

## Es gibt verschiedene Paketmanager

Natürlich gibt es nicht "den einen" Paketmanager. Verschiedene Distro Familien nutzen standardmäßig verschiedene Paketmanager. Auf Fedora-Systemen, also auch deinem Rechner, ist dies standardmäßig `dnf`. Auf Distros aus der Debian Familie ist dies `apt`. Außerdem gibt es zum Beispiel auch `flatpak`, ein Paketmanager welcher auf so gut wie allen Distros genutzt werden kann.

Flatpak legt einen großen Fokus auf Kompatibilität. Das bedeutet: Wenn du eine App nicht über dnf installieren kannst, geht es sehr wahrscheinlich mit Flatpak. Aus technischer Sicht ist dies möglich, weil ein Flatpak (so wird eine App genantt, die über den Flatpak Paketmanager installiert wird) sehr stark vom System isoliert ist. Praktisch bedeutet dies, dass die Flatpak Version eine App oft deutlich mehr Speicherplatz benötigt, als die Version von anderen Paketmanagern. Unter Umständen funktionieren aufgrund der Isolation gewisse Funktionen der App nicht korrekt - ob dies ein Problem ist, hängt jedoch stark von der App ab. 

## Welchen Paketmanager sollte ich also nutzen?

Primär solltest du probieren, den Paketmanager zu nutzen der Standardmäßig mit deinem System kommt: Für Fedora also `apt`. Die Pakete hier sind speziell für Fedora optimiert und getestet. Wenn du ein Paket benötigst welches hier nicht zu finden ist (was leider auch gar nicht so selten vorkommt), empfiehlt sich für dieses Paket Flatpak. So entsteht am Ende im Optimalfall ein Setup, in welchem der größte Teil deiner Pakete durch dnf gemanaged sind und ein kleiner Teil durch Flatpak. Wir erinnern uns: Ein großer Vorteil von Paketmanagern ist ja die Zentralisierung. Auf diese Weise erhalten wir so viel Zentralisierung wie möglich, um Dinge wie updates so einfach wie möglich zu machen.

> [!NOTE]
> Das Software Centre nutzt übrigens auch sowohl dnf wie auch Flatpak. Oben rechts können wir für eine bestimmte App auswählen, welcher Paketmanager für die jeweilige App genutzt werden soll - natürlich unter der Voraussetzung, dass das Paket bei mehreren Paketmanagern existiert.
> ![](99%20assets/Pasted%20image%2020251220095956.png)