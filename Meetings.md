# Notizen für Meetings

- [04.04.](#040424)
- [18.04.](#180424)
- [06.06.](#060624)
- [13.06.](#130624)
  
## 04.04.24

- FMOD eingerichtet
  - wäre auch ein interessantes Thema für Game Engines Technologienliste
- Quest verbunden, mit Kabel und Meta App funktioniert alles
- Audiotracks in FMOD arrangiert und verlinked
- TODO:
  - Raum in Unity bauen
  - FMOD Projekt integrieren
  - Steuerung implementieren
  - evtl. Visualizer

## 18.04.24

- Audio funktioniert
- Spatializing ist korrekt
  - Richtung der Audiospuren stimmt
  - Entfernung verringert die Lautstärke
- Steuerung funktioniert teilweise
  - Audiospuren sind bewegbar
  - werfen und heranziehen funktioniert noch nicht
- TODO:
  - Quest zurücksetzten 
  - Steuerung fertig
  - Visualizer
  - je nach verbleibender Zeit mit Occlusion anfangen

## 06.06.24

- Tropfsteinhöhle als Prototyp:
  - Hässlich aber funktioniert
  - Tropfen werden random generiert und erzeugen Aufprallgeräusch bei Kollision
  - Convolusion Reverb als Hall -> natürlicher Sound aber etwas Rechenintensiver
- Übergang von Hallzonen Innen <--> Aussen
  - schöner als gängige Snapshot Lösung
- Fackel mit Sound
  - Licht flackert reaktiv zum Audiofile
  - Bewegung der Fackel erzeugt "Whoosh"
  - noch nicht 100% ausgereift, zu schnelle Bewegung bringt PC zum Absturz
- gefunden, warum Visualizer nicht funktioniert hat:
  - FMOD bietet zwei Spacializer Möglichkeiten: 3D und Objekt
  - 3D ist akkurater weil es Plattformspeziefische Surroundsoundtechniken nutzt
  - dabei wird der Sound aber aus der FMOD Pipeline herausgenommen
    --> der DSP kann keinen Sound verarbeiten, der nicht bei ihm ankommt
  - mit normalen Spacializer funktioniert der Visualizer
- TODO:
  - VR Bewegung?
    - Laufen --> In VR eher schlecht, aber für Sound interessanter (Schritte auf unterschiedlichen Bodenmaterialien/gradueller Übergang bei Hallzonen)
    - Teleportieren --> Für VR einfacher, aber akustisch eher uninteressant
  - Fackel ausarbeiten
  - Occlusion
  - schönere Grafik?
  - mehr Räume

## 13.06.24

- Tropfsteinhöhle ausmodelliert
- Terrain als Spielwelt
- Hallzonen beachten jetzt Drehung des Kopfes
- Fackel lässt sich greifen, hat aber Offset
- TODO:
  - Bewegung: 
    - Locomotive Interaction ist von OVR vorhanden, funktioniert aber noch nicht
    - Schrittsounds sind schwer mit Spielerbewegung zu synchronisieren
  - Occlusion
  - mehr Räume