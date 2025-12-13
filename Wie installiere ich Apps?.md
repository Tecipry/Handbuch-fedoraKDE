
Wenn du dein System schon etwas erkundet hast, wirst du wahrscheinlich auf das Software Centre gestoßen sein.

![](99%20assets/Pasted%20image%2020251213152023.png)

"Ich nutze also einfach diese App" wirst du dir denken. Und es spricht auch grundsätzlich nichts dagegen, deine Apps hier herunterzuladen und zu managen. Wenn du jedoch etwas tiefer in das Thema eintauchen willst, solltest du hier weiterlesen.

# Der Paketmanager

Wie der Name vermuten lässt, ist ein Paketmanager (oder englisch: package manager) dafür zuständig, Pakete auf dem System zu verwalten. Ein Paket kannst du dir vereinfacht als eine App vorstellen - auch wenn dies eigentlich nicht richtig ist. Mit einem Paketmanager werden Pakete (also quasi Apps) installiert, verwaltet, und gelöscht. 

Aber was bringt dir das? Lass uns einen Blick auf die Installation und anschließende Deinstallation einer App unter windows und unter Fedora mit dem Paketmanager `apt` werfen, um zu verstehen warum ein Paketmanager so unglaublich praktisch ist. Wir werden das ganze am Beispiel der App `Zen` machen. Dies ist ein browser, welcher auf Firefox basiert.

### Installation und Deinstallation einer App unter Windows

1. Beschaffung der Installationsdatei
	Zuerst benötigen wir unsere Installationsdatei. Hierzu suchen wir online zum Beispiel nach "Zen Browser download" und stoßen auf die Website [www.zen-browser.app](https://zen-browser.app/). Unter "Download" bekommen wir eine `.exe` Installationsdatei. Bei verschiedenen Programmen könnte dies jedoch auch eine `.msi` Datei sein, oder etwas völlig anderes.

2. Der setup wizard
	Beim Ausführen der Installationsdatei startet der setup wizard. Nachdem wir uns durch das Menü geklickt haben, beginnt die eigentliche Installation. Im Hintergrund werden dabei hauptsächlich Dateien heruntergeladen und an verschiedenen Positionen im Dateisystem abgelegt.

3. Starten der App
	Nun ist die App installiert und kann normal gestartet werden. Für dieses Beispiel werden wir die App als nächstes allerdings wieder deinstallieren.

4. Deinstallation
	Wo fangen wir überhaupt hier an? 
	Der wahrscheinlich einfachste Weg beginnt in den Einstellungen: Unter "Apps" findet sich eine (mehr oder weniger vollständige) Liste der installierten Apps. Mit etwas Glück können wir hier die App auswählen und auf "Deinstallieren" drücken. Mit etwas Pech findet sich unsere App allerdings nicht in dieser Liste. 
	Da haben wir aber Glück, dass unser Betriebssystem eigentlich nur ein Skin für ältere Windows Versionen ist. Deshalb können wir über die Systemsteuerung zu den installierten Apps navigieren, um hier auf "Deinstallieren" zu drücken. Aber auch hier müssen wir hoffen, dass Microsoft uns wohlgesonnen ist - bei verschiedenen vorinstallierten Apps ist das ganze nämlich auch hier nicht möglich.

5. Der setup wizard, again
	Durch das drücken auf den "Deinstallieren" Knopf startet der setup wizard der App. Diesmal allerdings führt er uns durch den Deinstallationsprozess. Erneut können wir uns also durch die Menüs klicken, bis wir am Ende die App deinstalliert haben.

6. Aufräumen
	Oft werden bei der Deinstallation nicht alle Daten des Programms gelöscht. Zum Beispiel bleiben oft Konfigurationsdateien auf dem System zurück. Dies ist grundsätzlich eine praktische Sache: Sollten wir das Programm zu einem späteren Zeitpunkt erneut installieren, können diese Dateien genutzt werden um unter anderem Einstellungen wieder herzustellen.
	Es gibt aber Fälle, in denen wir wirklich alles was zum Programm gehört von unserem System löschen wollen. Es beginnt also die manuelle Jagd nach diesen verwaisten Dateien... und dafür müssen wir an einigen Stellen schauen. Hier nur eine Auswahl an Orten, an denen sich noch Dateien von unserem Programm finden könnten:
	
	```txt
	C:\Program Files\...
	C:\Program Files (x86)\...
	C:\ProgramData\...
	C:\Users\<USER>\AppData\Roaming\...
	C:\Users\<USER>\AppData\Local\...
	```
	
	Viel Spaß ;D

### Installation und Deinstallation einer App mit dem Paketmanager `apt`

1. Installation der App
	Öffne ein Terminal und führe dort folgenden Befehl aus:
	```sh
	sudo dnf install zen
	```