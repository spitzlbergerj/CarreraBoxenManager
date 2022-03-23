Achtung: Work in Progress - ich bin noch nicht fertig - es sind noch Korrekturen, Verbesserungen, Hinweise notwendig

# CarreraBoxenManager
Bedienkonsole für eine Boxengasse mit Garagenausfahrten und Safety Car Parkplatz - 3D-Drucke, Schaltung

![3D-Ansicht](https://raw.githubusercontent.com/spitzlbergerj/CarreraBoxenManager/main/images/AnsichtVorne.png)  

![vollständige Pit Lane mit Garagenausfahrten](https://raw.githubusercontent.com/spitzlbergerj/CarreraBoxenManager/main/images/Boxengasse-Garagen.png) 
(c) Garagenausfahrten Sebastian Möller, Laage, Comeo - https://www.slottrackparts.de/

# Wiki mit Details zur Entwicklung und dem Zusammenbau
Bitte das **[Wiki](https://github.com/spitzlbergerj/CarreraBoxenManager/wiki)** beachten! 


# Ziele: Einfache Fahrzeugcodierung - Safety Car Parkplatz

Nach vielen Stunden CAD Design, 3D Druck und Löten ist er nun fertig, mein BoxenManager. Die Idee dazu entstand, weil mir die übliche Methode zur Fahrzeugcodierung nicht wirklich gefiel und weil sich die Garageneinfahren von Comeo geradezu anboten, sie für eine elegante Codierung zu nutzen.

## Eigenschaften und Funktionen:
- Gehäuse im Stil der CU, montiert auf Randstreifen Standardgerade
- LEDs zur Zustandsanzeige der Garagen
- Schiebeschalter im Stil der CU mit 3 Stellungen für
	- Garage stromlos
	- Garage stromversorgt zur Fahrzeugcodierung
	- Garage stromversorgt, Hinterachse angehoben zur Fahrzeugcodierung und Test
- Hebevorrichtung für die Hinterachse, so dass nach der Codierung der Handregler getestet werden kann, ohne dass das Fahrzeug die Garage verlässt
- Abschaltung der Stromversorgung des Safety Car Parkplatzes sobald eine Garage stromversorgt wird. Damit kann das Safety Car während der Codierungen auf der Bahn bleiben
- einfachste Elektronik aus Schiebeschaltern, LEDs, Vorwiderständen, Magneten zur Hinterachsanhebung sowie einem 8-fach NOR-Gatter und einem Relais für den Safety Car Parkplatz 
- Flachbandkabel zur Verbindung BoxenManager mit den Garagen
- Verteiler für die Zusatzeinspeisungen an der Garage

# Details

## BoxenManager
- Randstreifen Standardgerade als Montagebasis
- 3D gedrucktes Gehäuse im CU Stil
- 8 Schrauben zur Montage des Gehäuses auf dem Randstreifen Standardgerade 
- 6 RGB - LEDs
- 6 Schiebeschalter mit je 3 Positionen
- Randstreifen muss nur an wenigen Stellen geschlitzt werden
- Stromversorgung über Zusatzeinspeisungsklammern
- Technische Zeichnung zur Bestimmung der Position der Schraubenlöcher
- Technische Zeichnung zur Bestimmung der Position der LEDs auf den platinen
- 4 Standardplatinen Lochraster 20 x 80 mm

## Schiebeschalter:
- Links
	- zugehörige Garage stromlos, LED aus, Safety Car Parkplatz stromversorgt
	- normaler Rennbetrieb 
- Mitte (nur eine Garage!) 
	- zugehörige Garage stromversorgt, LED grün, Safety Car Parkplatz stromlos
	- Fahrzeugcodierung für Fahrzeug in zugehöriger Garage
- Rechts (nur eine Garage; falls mehrere, dann nur Test, keine Codierung!)
	- zugehörige Garage stromversorgt, LED blau, Hinterachse in der Garage angehoben, Safety Car Parkplatz stromlos
	- Fahrzeugcodierung soweit Test des Handregler, ohne dass das Fahrzeug aus der Garage fährt, so dass weitere Codierungen nach Umschalten auf die nächste Garage möglich sind

## Garageneinfahren von Comeo
- Design und Fertigung der 60° Einfahren von Sebastian Möller, Laage, Comeo - https://www.slottrackparts.de/
- 1/2 einspurige Gerade als "Garage"
- Linke Schiene (Pluspol) der Einfahrt nicht mit der Bahn sondern mit BoxenManager verbunden
- Hebevorrichtung für Hinterachse aus 3D Druck und E-Magnet, der vom BoxenManager angesteuert wird

![Garagenausfahrten](https://raw.githubusercontent.com/spitzlbergerj/CarreraBoxenManager/main/images/Garagenausfahrt.png) 

![Garagenausfahrt](https://raw.githubusercontent.com/spitzlbergerj/CarreraBoxenManager/main/images/Garagenausfahrt-schraeg.png) 

(c) Garagenausfahrten, teilweise noch Entwicklungsversionen, Sebastian Möller, Laage, Comeo - https://www.slottrackparts.de/

## Boxengasse aus 3 Carrera Pitlanes
- 2 Tankplätze
- Safety Car Parkplatz 
- 6 Garageneinfahren
- 1/3 Geraden vor den Boxeneinfahrten zum sicheren Auslösen der Weichen 
- Kreuzung damit beide Tankplätze unabhängig angefahren werden können 
- Entkoppelung der ersten beiden Boxeneinfahrten

## Verkabelung Boxenmanager und Garagen
- 16 Pol Stecker zur Verbindung zwischen BoxenManager und dem Verteilergehäuse an den Garagen über ein Flachbandkabel
- 2 poliges Kabel für Zusatzeinspeisungsversorgung von der CU zum Verteilergehäuse ZE

## Garagengehäuse, Verteilergehäuse, Garagendächer
- Standard-Einspurgeraden wurden mittig im Winkel von 60° geteilt
- Am Ende jeder Einspurgerade-Häften befindet sich ein Gehäuse
- In diesem Gehäuse befindet sich der Hebemagnet, das Schaltrelais für die Stromversorgung der Garage sowie weitere Verkabelung
- Auf der Einspurgeraden ist eine Hebevorrichtung für die Hinterachse der Fahrzeuge moniert. Montage nur durch Einstecken eines Achsaufnahme in den Slot
- Zwischen den Schienenendgehäusen befinden sich Verteilergehäuse frü den Boxenmanager, die Zusatzeinspeisung sowie für die Steuerung der Stromversorgung des Safety Car Parkplatzes

## Safety Car parkplatz
- 3. Boxeneinfahrt 
- nicht entkoppelt, damit das Safety Car nach Einfahrt stehen bleibt
- Codierleitung jedoch unterbrochen und mit einem Schaltrelais auf NC (normally closed) verbunden
- Das Schaltrelais wird über ein ODER-Gatter angesteuert. Ist eine der Garagen stromversorgt, schaltet das Relais und unterbricht dadurch die Stromzufuhr zum Parkplatz

## Flachbandkabel
- Der Leitungsquerschnitt ist für die Steuerungssignale ausreichend
- die Garagenschienen und der SafgetyCar parkplatz werden über Relais mit dem normalen Bahnstrom versorgt
- Lediglich der Magnet wird direkt über das Flachbandkabel stromversorgt
- Eignet sich gut, um viele Adern unter den Schienen zu führen

## Braucht man den BoxenManager?
- Nein!
- Es war aber ein Riesenspaß das Gehäuse möglichst originalgetreu zu designen
- Ich habe unendlich viel gelernt in der Bedienung von FreeCAD
- Das Gehäuse können nun auch andere für ggf. sinnvollere Erweiterungen genutzt werden
- Das praktische Begreifen der Hebelgesetze und die Suche nach Möglichkeiten mit kleinen Hebelwegen die Fahrzeuge effektiv anzuheben war herausfordernd und hat wieder viel Spaß gemacht
