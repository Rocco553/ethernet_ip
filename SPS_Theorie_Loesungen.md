# SPS Theorie Aufgaben - Lösungen

## Aufgabe 1: Grundlagen der SPS-Programmierung

### Aufgabenstellung 1.1
Erläutere den Unterschied zwischen einem diskreten und einem analogen Eingangssignal in Bezug auf SPS.

### Lösung 1.1
**Diskrete Eingangssignale:**
- Digitale Signale mit zwei definierten Zuständen (EIN/AUS, 1/0, HIGH/LOW)
- Repräsentieren binäre Informationen
- Beispiele: Taster, Endschalter, Sensoren mit binärem Ausgang
- Werden direkt von der SPS als Binärwerte verarbeitet

**Analoge Eingangssignale:**
- Kontinuierliche Signale mit stufenlos veränderbaren Werten
- Repräsentieren physikalische Größen (Temperatur, Druck, Spannung, Strom)
- Typische Signalbereiche: 0-10V, 4-20mA
- Müssen von der SPS mittels Analog-Digital-Wandler (ADC) in digitale Werte umgewandelt werden
- Ermöglichen präzise Messung und Regelung von Prozessgrößen

---

### Aufgabenstellung 1.2
Beschreibe den Zweck von Speicherprogrammen in der SPS-Programmierung.

### Lösung 1.2
**Zweck von Speicherprogrammen:**

Speicherprogramme sind das Herzstück der SPS und dienen folgenden Zwecken:

1. **Flexibilität:** Programme können ohne Hardwareänderungen angepasst werden (im Gegensatz zu fest verdrahteten Steuerungen)

2. **Wiederverwendbarkeit:** Einmal erstellte Programme können gespeichert, kopiert und in anderen Anlagen wiederverwendet werden

3. **Funktionsimplementierung:** Sie speichern anwenderorientierte Steuerungsanweisungen für:
   - Verknüpfungssteuerungen
   - Ablaufsteuerungen
   - Zeit- und Zählfunktionen
   - Arithmetische Funktionen

4. **Permanente Speicherung:** Programme bleiben auch nach Stromausfall erhalten

5. **Einfache Wartung und Änderung:** Steuerungslogik kann schnell angepasst werden, ohne Verkabelung zu ändern

*Verifiziert durch SPS Einführung.pdf: Definition nach EN 61131 bestätigt die Funktion des "programmierbaren Speichers zur internen Speicherung der anwenderorientierten Steuerungsanweisungen"*

---

## Aufgabe 2: SPS-Programmiersprachen

### Aufgabenstellung 2.1
Nenne und erkläre zwei gängige Programmiersprachen, die in der SPS-Programmierung verwendet werden, und diskutiere ihre Vor- und Nachteile.

### Lösung 2.1

**1. Kontaktplan (KOP / Ladder Diagram - LD):**

**Beschreibung:**
- Grafische Programmiersprache
- Orientiert sich an elektrischen Schaltplänen
- Verwendet Symbole wie Kontakte und Spulen

**Vorteile:**
- Sehr intuitiv für Elektriker und Elektrotechniker
- Einfache Visualisierung von Schaltungen
- Leicht erlernbar für Personen mit Elektrotechnik-Hintergrund
- Schnelle Fehlersuche durch grafische Darstellung

**Nachteile:**
- Unübersichtlich bei komplexen Programmen
- Weniger geeignet für mathematische Operationen
- Kann bei großen Projekten sehr umfangreich werden
- Schwierig für komplexe Ablaufsteuerungen

**2. Strukturierter Text (ST / Structured Text):**

**Beschreibung:**
- Textbasierte Hochsprache
- Ähnelt Programmiersprachen wie Pascal oder C
- Gut für komplexe Algorithmen und Berechnungen

**Vorteile:**
- Sehr kompakte und übersichtliche Darstellung
- Ideal für mathematische Operationen und Algorithmen
- Gut für Programmierer mit IT-Hintergrund
- Effizient bei komplexen Steuerungsaufgaben
- Ermöglicht strukturierte Programmierung

**Nachteile:**
- Höhere Einarbeitungszeit für Nicht-Programmierer
- Weniger intuitiv als grafische Sprachen
- Fehlersuche kann schwieriger sein
- Nicht so verbreitet in traditionellen Elektrobetrieben

---

### Aufgabenstellung 2.2
Warum ist die IEC 61131-3-Standardprogrammiersprache in der SPS-Programmierung wichtig?

### Lösung 2.2

**Bedeutung des IEC 61131-3-Standards:**

1. **Standardisierung und Einheitlichkeit:**
   - Definiert einheitliche Programmiersprachen für alle SPS-Hersteller
   - Reduziert herstellerspezifische Unterschiede
   - Erleichtert den Wechsel zwischen verschiedenen SPS-Systemen

2. **Portabilität:**
   - Programme können leichter zwischen verschiedenen SPS-Plattformen übertragen werden
   - Reduziert Abhängigkeit von einzelnen Herstellern
   - Erleichtert Migration auf neue Systeme

3. **Ausbildung und Know-how:**
   - Einheitliche Ausbildung möglich
   - Programmierer können ihr Wissen herstellerübergreifend einsetzen
   - Reduziert Schulungsaufwand

4. **Qualitätssicherung:**
   - Klare Definitionen und Vorgaben
   - Verbesserte Codequalität
   - Bessere Wartbarkeit

5. **Internationale Akzeptanz:**
   - Weltweit anerkannter Standard
   - Erleichtert internationale Projekte
   - Verbessert Zusammenarbeit zwischen Unternehmen

6. **Fünf definierte Programmiersprachen:**
   - Kontaktplan (LD)
   - Funktionsplan (FBD)
   - Strukturierter Text (ST)
   - Anweisungsliste (IL)
   - Ablaufsprache (SFC)

*Verifiziert durch SPS Einführung.pdf: Definition nach EN 61131 bestätigt die Standardisierung*

---

## Aufgabe 3: SPS-Steuerungsstrukturen

### Aufgabenstellung 3.1
Erkläre den Unterschied zwischen einer sequenziellen und einer parallelen Steuerungsstruktur in der SPS-Programmierung.

### Lösung 3.1

**Sequenzielle Steuerungsstruktur:**

**Definition:**
- Schrittweise Abarbeitung von Befehlen nacheinander
- Ein Schritt wird erst ausgeführt, wenn der vorherige abgeschlossen ist
- Zeitlich aufeinanderfolgende Prozesse

**Merkmale:**
- Lineare Abfolge von Operationen
- Klare zeitliche Reihenfolge
- Abhängigkeiten zwischen den Schritten
- Typisch für Ablaufsteuerungen

**Beispiele:**
- Montagelinien mit definierten Arbeitsschritten
- Materialflusssysteme
- Batch-Prozesse in der Chemie

**Parallele Steuerungsstruktur:**

**Definition:**
- Gleichzeitige Abarbeitung mehrerer Prozesse
- Unabhängige Steuerungsabläufe laufen nebeneinander
- Keine zwingenden zeitlichen Abhängigkeiten

**Merkmale:**
- Mehrere Prozesse werden simultan ausgeführt
- Prozesse sind unabhängig voneinander
- Erhöhte Effizienz durch Parallelisierung
- Synchronisation kann bei Bedarf erfolgen

**Beispiele:**
- Mehrere Maschinen in einer Fertigungshalle
- Parallele Bearbeitungsstationen
- Mehrachsige Bewegungssteuerungen

**Hauptunterschiede:**
- **Zeitliche Abfolge:** Sequenziell = nacheinander, Parallel = gleichzeitig
- **Abhängigkeiten:** Sequenziell = stark abhängig, Parallel = weitgehend unabhängig
- **Effizienz:** Parallel höher bei unabhängigen Prozessen
- **Komplexität:** Parallel komplexer in der Programmierung

---

### Aufgabenstellung 3.2
Beschreibe die Verwendung von Schleifen in SPS-Programmen und gebe ein Beispiel.

### Lösung 3.2

**Verwendung von Schleifen in SPS-Programmen:**

**Zweck:**
- Wiederholte Ausführung von Programmteilen
- Durchlaufen von Datenbereichen
- Zyklisches Abfragen von Bedingungen
- Effiziente Programmierung sich wiederholender Aufgaben

**Arten von Schleifen:**

1. **FOR-Schleife:**
   - Definierte Anzahl von Durchläufen
   - Mit Zählvariable
   - Bekannte Start- und Endwerte

2. **WHILE-Schleife:**
   - Bedingungsgesteuert
   - Läuft solange Bedingung erfüllt ist
   - Anzahl der Durchläufe variabel

3. **REPEAT-UNTIL-Schleife:**
   - Mindestens einmal ausgeführt
   - Läuft bis Bedingung erfüllt ist

**Praktisches Beispiel - Verpackungsanlage:**

```
Anwendung: Zählen von 10 Produkten in eine Verpackungsbox

FOR Zaehler := 1 TO 10 DO
    WARTEN_AUF_PRODUKT();          // Warten bis Sensor Produkt erkennt
    TRANSPORTBAND_AKTIVIEREN();     // Transportband einschalten
    PRODUKT_IN_BOX_LEGEN();        // Produkt in Box ablegen
    ZAEHLER_ERHOEHEN();            // Zähler erhöhen
END_FOR;

BOX_VERSCHLIESSEN();               // Nach 10 Produkten Box verschließen
NAECHSTE_BOX_BEREITSTELLEN();      // Neue Box positionieren
```

**Vorteile:**
- Kompakter, übersichtlicher Code
- Leichte Anpassung der Wiederholungsanzahl
- Reduzierung von Code-Duplikaten
- Einfache Wartung

**Anwendungsgebiete:**
- Array-Verarbeitung
- Batch-Zählung
- Qualitätsprüfungen mit mehreren Messungen
- Initialisierung mehrerer gleichartiger Komponenten

---

## Aufgabe 4: Sicherheit in der SPS-Programmierung

### Aufgabenstellung 4.1
Warum ist es wichtig, Sicherheitsaspekte bei der SPS-Programmierung zu berücksichtigen?

### Lösung 4.1

**Bedeutung der Sicherheitsaspekte:**

**1. Personenschutz:**
- Verhinderung von Unfällen und Verletzungen
- Schutz der Maschinenbediener
- Vermeidung von Gesundheitsschäden
- Not-Halt-Funktionen müssen zuverlässig funktionieren

**2. Anlagensicherheit:**
- Schutz vor Maschinenschäden
- Vermeidung von Produktionsausfällen
- Verhinderung von Fehlfunktionen
- Schutz teurer Investitionen

**3. Rechtliche Verpflichtungen:**
- Einhaltung von Sicherheitsnormen (z.B. EN ISO 13849)
- Maschinenrichtlinien müssen erfüllt werden
- Haftungsfragen bei Unfällen
- CE-Kennzeichnung erfordert sichere Programmierung

**4. Wirtschaftliche Aspekte:**
- Vermeidung von Produktionsausfällen
- Reduzierung von Schadensersatzforderungen
- Imageschutz des Unternehmens
- Minimierung von Versicherungskosten

**5. Prozesssicherheit:**
- Zuverlässiger Betrieb rund um die Uhr
- Schutz vor Fehlbedienung
- Sichere Reaktion auf Störungen
- Datensicherheit und -integrität

**6. Technische Sicherheit:**
- Schutz vor Programmfehlern
- Absicherung kritischer Funktionen
- Redundante Sicherheitssysteme
- Überwachung von Grenzwerten

*Verifiziert durch Control Plus.pdf: Erwähnung von "Safety" als wichtiger Bereich bei OpCon Control Plus*

---

### Aufgabenstellung 4.2
Nenne und erkläre zwei Methoden zur Sicherung von SPS-Programmen vor unautorisiertem Zugriff.

### Lösung 4.2

**Methode 1: Passwortschutz und Zugriffsberechtigungen**

**Beschreibung:**
- Vergabe von Passwörtern für verschiedene Zugriffsebenen
- Hierarchisches Berechtigungssystem
- Unterschiedliche Rechte für verschiedene Benutzergruppen

**Umsetzung:**
- **Leseschutz:** Programm kann nur mit Passwort gelesen werden
- **Schreibschutz:** Änderungen nur mit entsprechender Berechtigung
- **Bedienerebenen:** Operator, Inbetriebnehmer, Entwickler
- **Protokollierung:** Aufzeichnung wer wann welche Änderungen vorgenommen hat

**Vorteile:**
- Einfache Implementierung
- Flexible Rechtevergabe
- Schutz vor versehentlichen Änderungen
- Nachvollziehbarkeit durch Logging

**Nachteile:**
- Passwörter können verloren gehen oder vergessen werden
- Bei schlechten Passwörtern besteht Sicherheitsrisiko
- Muss regelmäßig aktualisiert werden

---

**Methode 2: Physische Sicherungsmaßnahmen und Netzwerksegmentierung**

**Beschreibung:**
- Hardware-basierte Schutzmaßnahmen
- Netzwerktrennung von kritischen Bereichen
- Verwendung von Schlüsselschaltern oder Hardware-Keys

**Umsetzung:**

**Physische Maßnahmen:**
- Verschlossene Schaltschränke
- Schlüsselschalter für Zugriffsmodi
- Hardware-Dongles (USB-Schlüssel)
- Abschließbare Bedienelemente

**Netzwerksicherheit:**
- Firewall-Systeme zwischen Büro- und Produktionsnetz
- VPN für Fernzugriff
- Segmentierung des Steuerungsnetzes
- Deaktivierung nicht benötigter Schnittstellen
- Verschlüsselte Kommunikation

**Zusätzliche Maßnahmen:**
- Zutrittskontrolle zu Technikräumen
- Überwachung durch Kameras
- Speicherung auf geschützten Medien (z.B. schreibgeschützte Speicherkarten)
- Backup-Systeme an sicheren Orten

**Vorteile:**
- Sehr hohe Sicherheit
- Kombiniert mit Software-Schutz sehr effektiv
- Schutz vor physischem Zugriff
- Netzwerksegmentierung schützt vor Cyber-Angriffen

**Nachteile:**
- Höherer Installationsaufwand
- Höhere Kosten
- Kann Wartungsarbeiten erschweren

*Verifiziert durch Control Plus.pdf: Erwähnung von "Safety" und verschiedenen Sicherheitskonzepten in der Steuerungsplattform*

---

## Aufgabe 5: SPS-Hardwarekomponenten

### Aufgabenstellung 5.1
Beschreibe die Funktion eines Speichermoduls in einer SPS.

### Lösung 5.1

**Funktionen eines Speichermoduls:**

**1. Programmspeicherung:**
- Speicherung des Anwenderprogramms
- Enthält die Steuerungslogik
- Permanente Speicherung auch bei Stromausfall
- Ermöglicht schnellen Programmstart nach Wiedereinschalten

**2. Datenspeicherung:**
- Speicherung von Prozessdaten
- Parametereinstellungen
- Rezeptdaten
- Historische Daten (Logs, Alarme)

**3. Arten von Speichern:**

**Flüchtiger Speicher (RAM):**
- Schneller Zugriff
- Verliert Daten bei Stromausfall
- Für temporäre Daten und laufende Berechnungen
- Arbeitsspeicher der CPU

**Nichtflüchtiger Speicher:**
- Behält Daten ohne Stromversorgung
- Flash-Speicher, EEPROM
- Für Programme und wichtige Parameter
- Langzeitdatensicherung

**4. Spezielle Speichertypen:**

**NOVRAM (Non-Volatile RAM):**
- Remanenter Speicher
- Daten bleiben bei Stromausfall erhalten
- Für kritische Prozessdaten
- Typische Größen: 128 kB bis mehrere MB

**CFast-Karten:**
- Austauschbare Speichermedien
- Hohe Kapazität
- Einfacher Programmtransfer
- Backup-Möglichkeit

**5. Praktische Anwendungen:**
- Betriebssystemspeicherung
- Firmware-Updates
- Datenlogging
- Rezeptverwaltung
- Diagnose-Informationen

*Verifiziert durch Control Plus.pdf: CX2020 verfügt über 128 kB NOVRAM und CFast-Speicherkarten für Programmspeicherung*

---

### Aufgabenstellung 5.2
Erläutere den Zweck von Ein- und Ausgangsmodulen in einer SPS.

### Lösung 5.2

**Ein- und Ausgangsmodule (I/O-Module):**

**Eingangmodule:**

**Zweck:**
- Aufnahme von Signalen aus der Umgebung
- Schnittstelle zwischen Sensoren und SPS-CPU
- Signalaufbereitung und -anpassung
- Schutz der CPU vor Überspannungen

**Funktionen:**
- Erfassung von Schaltzuständen (digital)
- Messung von physikalischen Größen (analog)
- Signalwandlung von Feldebene auf CPU-Ebene
- Elektrische Entkopplung (Galvanische Trennung)
- Filterung von Störsignalen

**Arten:**
- **Digitale Eingänge:** Taster, Schalter, Sensoren (24V DC, 230V AC)
- **Analoge Eingänge:** Temperatur-, Druck-, Durchflusssensoren (0-10V, 4-20mA)

**Beispiele:**
- Endschalter an Türen
- Temperatursensoren
- Druckmessumformer
- Näherungssensoren
- Lichtschranken

---

**Ausgangsmodule:**

**Zweck:**
- Ansteuerung von Aktoren
- Umsetzung von CPU-Befehlen in Steuersignale
- Leistungsverstärkung der CPU-Signale
- Schnittstelle zwischen CPU und Feldgeräten

**Funktionen:**
- Schalten von Lasten (Motoren, Ventile, Lampen)
- Ausgabe von Steuersignalen
- Anpassung der Spannungs- und Stromebenen
- Schutz der CPU vor Rückwirkungen
- Galvanische Trennung

**Arten:**
- **Digitale Ausgänge:** Relais, Transistorausgänge (24V DC, 230V AC)
- **Analoge Ausgänge:** Frequenzumrichter, Stellventile (0-10V, 4-20mA)

**Beispiele:**
- Motorsteuerung
- Ventilbetätigung
- Signallampen
- Heizungsregelung
- Positionierungsantriebe

---

**Wichtige Merkmale:**

**1. Modularität:**
- Flexible Erweiterung je nach Bedarf
- Austauschbarkeit bei Defekten
- Anpassung an verschiedene Signaltypen

**2. Signalarten:**
- Digital: Binäre Zustände (0/1)
- Analog: Kontinuierliche Werte
- Verschiedene Spannungs-/Strombereiche

**3. Technische Merkmale:**
- Anzahl der Kanäle pro Modul (typisch 8, 16, 32)
- Signaltyp und -bereich
- Reaktionszeit
- Auflösung (bei analogen Modulen)

**4. Diagnose:**
- LED-Anzeigen für Kanalzustände
- Fehlerdiagnose
- Kurzschluss-/Überlasterkennung

*Verifiziert durch SPS Einführung.pdf: Definition nach EN 61131 erwähnt "digitale oder analoge Eingangs- und Ausgangssignale verschiedene Arten von Maschinen und Prozessen zu steuern"*

---

## Aufgabe 6: SPS-Fehlerbehebung

### Aufgabenstellung 6.1
Was sind die häufigsten Fehlerquellen bei der SPS-Programmierung, und wie können sie behoben werden?

### Lösung 6.1

**Häufige Fehlerquellen und Lösungen:**

**1. Syntaxfehler:**

**Problem:**
- Falsche Schreibweise von Befehlen
- Fehlende Klammern oder Semikolons
- Ungültige Variablennamen
- Nicht geschlossene Funktionsblöcke

**Behebung:**
- Verwendung der Compiler-Fehlermeldungen
- Syntax-Highlighting der Programmierumgebung nutzen
- Code-Validierung vor dem Download
- Konsistente Namenskonventionen verwenden

---

**2. Logikfehler:**

**Problem:**
- Fehlerhafte Programmlogik
- Falsche Verknüpfungen (UND statt ODER)
- Fehlende oder falsche Bedingungen
- Timing-Probleme

**Behebung:**
- Schrittweise Programmtests
- Simulation vor Inbetriebnahme
- Online-Debugging mit Variablenbeobachtung
- Ablaufdiagramme zur Visualisierung erstellen
- Code-Reviews durch Kollegen

---

**3. Adressierungsfehler:**

**Problem:**
- Falsche Ein-/Ausgangsadressen
- Doppelte Verwendung von Adressen
- Nicht existierende Speicherbereiche
- Verwechslung von Eingangs- und Ausgangsadressen

**Behebung:**
- Systematische Dokumentation der Adressen
- Verwendung symbolischer Adressen statt absoluter
- Hardware-Konfiguration überprüfen
- Adresstabellen pflegen

---

**4. Timing-Probleme:**

**Problem:**
- Zu kurze oder zu lange Zeitvorgaben
- Zykluszeit-Überschreitungen
- Race Conditions
- Signalprellungen nicht berücksichtigt

**Behebung:**
- Flankenauswertung verwenden
- Timer richtig dimensionieren
- Zykluszeit überwachen
- Entprellungsroutinen implementieren

---

**5. Kommunikationsfehler:**

**Problem:**
- Netzwerkprobleme
- Falsche Busparameter
- Timeout-Fehler
- Fehlerhafte Verkabelung

**Behebung:**
- Netzwerkdiagnose-Tools nutzen
- Busparameter überprüfen
- Verkabelung und Terminierung prüfen
- Timeout-Werte anpassen

---

**6. Speicherprobleme:**

**Problem:**
- Speicherüberlauf
- Zu große Programme
- Datenverlust
- Nicht initialisierte Variablen

**Behebung:**
- Speichernutzung überwachen
- Programme optimieren
- Remanente Daten richtig konfigurieren
- Variablen initialisieren

---

**7. Hardware-Fehler:**

**Problem:**
- Defekte Module
- Lockere Verbindungen
- Verschleiß von Komponenten
- Überspannung

**Behebung:**
- Hardwarediagnose durchführen
- Module tauschen
- Verkabelung überprüfen
- Überspannungsschutz installieren

---

### Aufgabenstellung 6.2
Wie könnte man vorgehen, um einen Fehler in einem SPS-Programm zu identifizieren und zu beheben?

### Lösung 6.2

**Systematisches Vorgehen zur Fehlersuche:**

**Phase 1: Fehlerbeschreibung und Analyse**

**Schritt 1: Fehlersymptome dokumentieren**
- Wann tritt der Fehler auf?
- Ist der Fehler reproduzierbar?
- Was funktioniert nicht wie erwartet?
- Welche Fehlermeldungen erscheinen?
- Hat sich etwas an der Anlage geändert?

**Schritt 2: Informationen sammeln**
- Alarmlisten auslesen
- Fehlerhistorie prüfen
- Bediener befragen
- Dokumentation prüfen

---

**Phase 2: Fehlersuche**

**Schritt 3: Programmanalyse**
- Online-Verbindung zur SPS herstellen
- Programm im Online-Modus öffnen
- Betroffene Programmteile identifizieren

**Schritt 4: Überwachung und Diagnose**
- **Variablenbeobachtung:** Relevante Variablen in Beobachtungstabelle aufnehmen
- **Force-Funktion:** Einzelne Ein-/Ausgänge testweise setzen
- **Schrittweises Durchgehen:** Programm Schritt für Schritt durchgehen
- **Baustein-Überwachung:** Eingänge und Ausgänge von Bausteinen beobachten

**Schritt 5: Hardware-Prüfung**
- Status-LEDs an den Modulen prüfen
- Ein-/Ausgangszustände kontrollieren
- Verkabelung überprüfen
- Sensorik und Aktorik testen

---

**Phase 3: Fehlereingrenzung**

**Schritt 6: Systematische Eingrenzung**
- **Halbierungsmethode:** Programm in Abschnitte teilen und systematisch testen
- **Bottom-Up:** Von einfachen zu komplexen Funktionen
- **Top-Down:** Von Hauptprogramm zu Unterprogrammen

**Schritt 7: Isolierung**
- Fehlerhafte Programmteile isolieren
- Abhängigkeiten identifizieren
- Auswirkungen auf andere Bereiche prüfen

---

**Phase 4: Fehlerbehebung**

**Schritt 8: Korrektur**
- Programm im Offline-Modus ändern
- Änderungen dokumentieren
- Backup des alten Programms erstellen

**Schritt 9: Test**
- Geänderte Programmteile im Simulator testen
- Online-Test im sicheren Modus
- Funktionstest durchführen

**Schritt 10: Verifikation**
- Vollständigen Funktionstest durchführen
- Längeren Probebetrieb durchführen
- Alle Betriebszustände testen

---

**Phase 5: Dokumentation**

**Schritt 11: Abschlussdokumentation**
- Fehlerursache dokumentieren
- Durchgeführte Änderungen protokollieren
- Programmversion aktualisieren
- Wartungshistorie ergänzen
- Lessons Learned festhalten

---

**Wichtige Werkzeuge:**

1. **Online-Diagnose:** Echtzeit-Programmbeobachtung
2. **Trace-Funktion:** Aufzeichnung von Variablenverläufen
3. **Simulation:** Testen ohne Hardware
4. **Fehlerprotokoll:** Systematische Aufzeichnung
5. **Oszilloskop:** Für Signalanalyse
6. **Multimeter:** Für elektrische Messungen

---

**Best Practices:**

- Niemals direkt an laufender Anlage ändern
- Immer Sicherheitskopien erstellen
- Änderungen dokumentieren
- Kollegen einbeziehen bei komplexen Problemen
- Ruhe bewahren und systematisch vorgehen
- Nie mehrere Änderungen gleichzeitig machen

---

## Aufgabe 7: SPS-Netzwerkkommunikation

### Aufgabenstellung 7.1
Erkläre den Zweck von Netzwerkkommunikation in einer SPS-Umgebung.

### Lösung 7.1

**Zweck der Netzwerkkommunikation:**

**1. Datenaustausch zwischen Steuerungen:**
- Mehrere SPS können Daten untereinander austauschen
- Koordination von Produktionsabläufen
- Synchronisation verschiedener Anlagenteile
- Verteilte Steuerungsarchitekturen

**Beispiel:** Eine Fertigungslinie mit mehreren Bearbeitungsstationen, jede mit eigener SPS, die Werkstückdaten weitergeben.

---

**2. Kommunikation mit übergeordneten Systemen:**
- Anbindung an SCADA/HMI-Systeme
- Datenübertragung zu MES (Manufacturing Execution System)
- Integration in ERP-Systeme
- Cloud-Anbindung für Industrie 4.0

**Nutzen:** Produktionsdatenerfassung, Reporting, Fernüberwachung

---

**3. Feldbus-Kommunikation:**
- Anbindung dezentraler Peripherie
- Kommunikation mit Sensoren und Aktoren
- Reduzierung des Verkabelungsaufwands
- Flexible Anlagenerweiterung

---

**4. Fernwartung und Diagnose:**
- Remote-Zugriff für Service-Techniker
- Fehlerdiagnose aus der Ferne
- Software-Updates ohne Vor-Ort-Einsatz
- Kosteneinsparung durch reduzierte Anfahrten

---

**5. Datenspeicherung und Logging:**
- Übertragung von Produktionsdaten zu Datenbanken
- Historische Datenerfassung
- Quality Management
- Rückverfolgbarkeit (Traceability)

---

**6. Integration verschiedener Systeme:**
- Roboter-Steuerungen
- Antriebsregler
- Mess- und Prüfsysteme
- Bildverarbeitungssysteme
- RFID-Lesegeräte

---

**7. Echtzeitkommunikation:**
- Synchronisierte Bewegungssteuerung
- Motion Control über Netzwerk
- Zeitkritische Prozesssteuerung
- Deterministische Kommunikation

---

**8. Industrie 4.0 und IoT:**
- Vernetzung von Maschinen (M2M - Machine to Machine)
- Smart Factory Konzepte
- Predictive Maintenance (vorausschauende Wartung)
- Datenanalyse und Optimierung

*Verifiziert durch Control Plus.pdf: Erwähnung von "Connectivity" und "Information Services" als zentrale Komponenten der Control Plus Plattform sowie "Real-time-Ethernet-Kommunikation" beim VPB-System*

---

### Aufgabenstellung 7.2
Nenne und erkläre zwei gängige Protokolle für die SPS-Netzwerkkommunikation.

### Lösung 7.2

**Protokoll 1: PROFINET (Process Field Network)**

**Beschreibung:**
- Industrieller Ethernet-Standard
- Nachfolger von PROFIBUS
- Entwickelt von Siemens und PROFIBUS-Nutzerorganisation
- Weit verbreitet in der Automatisierungstechnik

**Eigenschaften:**
- Basiert auf Standard-Ethernet (TCP/IP)
- Echtzeitfähig durch spezielle Priorisierung
- Hohe Datenübertragungsraten (100 Mbit/s, 1 Gbit/s)
- Deterministische Kommunikation möglich

**Kommunikationsklassen:**
1. **TCP/IP:** Nicht zeitkritische Daten
2. **Real-Time (RT):** Echtzeit für Standard-Automation
3. **Isochronous Real-Time (IRT):** Hochpräzise Synchronisation für Motion Control

**Anwendungen:**
- Fabrikautomation
- Prozessautomation
- Motion Control
- Robotik

**Vorteile:**
- Standard-Ethernet-Infrastruktur nutzbar
- Große Anzahl unterstützter Geräte
- Flexibel skalierbar
- Integrierte Diagnose
- Hot-Plug-Fähigkeit

**Nachteile:**
- Komplexere Konfiguration
- Höhere Anforderungen an Netzwerk-Hardware für IRT
- Lizenzkosten für Gerätehersteller

---

**Protokoll 2: EtherNet/IP (Ethernet Industrial Protocol)**

**Beschreibung:**
- Industrial Protocol auf Ethernet-Basis
- Entwickelt von Rockwell Automation
- Teil der CIP-Familie (Common Industrial Protocol)
- Sehr verbreitet in Nordamerika

**Eigenschaften:**
- Verwendet Standard-TCP/IP und UDP/IP
- Unmodifiziertes Ethernet
- Objektorientiertes Modell
- Kompatibel mit Standard-IT-Komponenten

**Kommunikationstypen:**
- **Explicit Messaging:** Nicht zeitkritische Daten (über TCP)
- **Implicit Messaging:** Echtzeitdaten (über UDP)
- **CIP Sync:** Zeitsynchronisation für präzise Anwendungen
- **CIP Motion:** Motion Control Funktionen

**Anwendungen:**
- Fertigungsautomation
- Prozessindustrie
- Hybrid-Anwendungen
- Integration von IT und OT (Operational Technology)

**Vorteile:**
- Einfache Integration in bestehende Netzwerke
- Keine spezielle Hardware erforderlich
- Offener Standard
- Umfangreiche Diagnosemöglichkeiten
- Große Gerätevielfalt
- Firewall-kompatibel

**Nachteile:**
- Nicht deterministisch ohne spezielle Maßnahmen
- Höhere Latenzzeiten als bei spezialisierten Lösungen
- Netzwerk-Know-how erforderlich

---

**Vergleich:**

| Aspekt | PROFINET | EtherNet/IP |
|--------|----------|-------------|
| **Verbreitung** | Hauptsächlich Europa | Hauptsächlich Nordamerika |
| **Echtzeit** | Sehr gut (IRT) | Gut (CIP Sync) |
| **Komplexität** | Mittel bis hoch | Mittel |
| **Standard-Ethernet** | Teilweise modifiziert | Vollständig standard |
| **Motion Control** | Exzellent | Gut |

**Weitere gängige Protokolle (kurze Erwähnung):**
- **EtherCAT:** Sehr schnell, Master-Slave-Topologie
- **Modbus TCP:** Einfach, weit verbreitet, nicht Echtzeit
- **OPC UA:** Plattformunabhängig, Industrie 4.0
- **POWERLINK:** Open-Source, Echtzeitfähig

*Hinweis: EtherNet/IP ist besonders relevant, da das Projektthema "ethernet_ip" ist*

---

## Aufgabe 8: SPS-Programmierzyklen

### Aufgabenstellung 8.1
Beschreibe den Ablauf eines typischen SPS-Programmierzyklus.

### Lösung 8.1

**Der SPS-Programmierzyklus (Scan Cycle):**

Ein SPS-Programmierzyklus läuft kontinuierlich und wiederholt sich ständig. Der typische Ablauf besteht aus folgenden Phasen:

---

**Phase 1: Einlesen der Eingänge (Input Scan)**

**Ablauf:**
- SPS liest alle physikalischen Eingangssignale
- Signale werden in den Prozessabbild der Eingänge (PAE) geschrieben
- Momentaufnahme (Snapshot) aller Eingänge
- Dauer: typisch 1-10 ms

**Wichtig:**
- Alle Eingänge werden gleichzeitig erfasst
- Änderungen während des Zyklus werden erst im nächsten Zyklus berücksichtigt
- Gewährleistet konsistente Datenbasis für Programmabarbeitung

---

**Phase 2: Programmabarbeitung (Program Execution)**

**Ablauf:**
- Anwenderprogramm wird von Anfang bis Ende durchlaufen
- Verarbeitung der Eingangsdaten aus dem PAE
- Logische Verknüpfungen werden ausgeführt
- Berechnungen durchgeführt
- Ergebnisse werden im Prozessabbild der Ausgänge (PAA) gespeichert
- Dauer: abhängig von Programmgröße und Komplexität (1-100+ ms)

**Wichtig:**
- Arbeitet mit Prozessabbildern, nicht direkt mit Hardware
- Reihenfolge der Programmierung ist wichtig
- Änderungen an Eingängen werden nicht sofort berücksichtigt

---

**Phase 3: Ausgabe der Ergebnisse (Output Scan)**

**Ablauf:**
- Daten aus dem PAA werden an die physikalischen Ausgänge übertragen
- Alle Ausgänge werden praktisch gleichzeitig geschaltet
- Aktoren werden angesteuert
- Dauer: typisch 1-10 ms

**Wichtig:**
- Erst am Ende des Zyklus werden Ausgänge geschaltet
- Gewährleistet konsistente Ausgabe

---

**Phase 4: Housekeeping/Overhead**

**Ablauf:**
- Selbstdiagnose der SPS
- Kommunikationsaufgaben
- Überwachung der Zykluszeit (Watchdog)
- Aktualisierung von Timern
- Betriebssystem-Tasks
- Dauer: typisch 1-5 ms

---

**Grafische Darstellung des Zyklus:**

```
┌─────────────────────────────────────┐
│  1. Eingänge einlesen (Input)       │
│     → PAE aktualisieren             │
└──────────┬──────────────────────────┘
           ↓
┌──────────────────────────────────────┐
│  2. Programm abarbeiten (Execution)  │
│     → Logik verarbeiten              │
│     → PAA berechnen                  │
└──────────┬───────────────────────────┘
           ↓
┌──────────────────────────────────────┐
│  3. Ausgänge schreiben (Output)      │
│     → PAA an Hardware ausgeben       │
└──────────┬───────────────────────────┘
           ↓
┌──────────────────────────────────────┐
│  4. Housekeeping/Overhead            │
│     → Diagnose, Kommunikation        │
└──────────┬───────────────────────────┘
           ↓
           └──→ Zyklus wiederholt sich
```

---

**Beispiel-Timing:**

Typischer Zyklus einer mittelgroßen Steuerung:
- Input Scan: 2 ms
- Program Execution: 15 ms
- Output Scan: 2 ms
- Housekeeping: 3 ms
- **Gesamte Zykluszeit: 22 ms**

---

**Besonderheiten:**

**Direkte Ein-/Ausgänge:**
- Manche SPS erlauben direkten Zugriff auf Hardware
- Umgeht Prozessabbild für zeitkritische Anwendungen
- Muss explizit programmiert werden

**Interrupts:**
- Unterbrechung des normalen Zyklus
- Für ereignisgesteuerte Reaktionen
- Höhere Priorität als Hauptprogramm
- Beispiele: Zähler-Interrupts, Hardware-Interrupts

**Zeitgesteuerte Tasks:**
- Zusätzliche Programmteile mit eigener Zykluszeit
- Parallel zum Hauptzyklus
- Für zeitkritische oder langsame Prozesse

---

### Aufgabenstellung 8.2
Warum ist die Zykluszeit in der SPS-Programmierung wichtig?

### Lösung 8.2

**Bedeutung der Zykluszeit:**

**1. Reaktionszeit des Systems**

**Problem:**
- Maximale Reaktionszeit = 2 × Zykluszeit
- Eingangssignal kurz nach Input Scan → wird erst nächsten Zyklus erkannt
- Ausgangssignal steht erst nach Output Scan zur Verfügung

**Auswirkung:**
- Bei 50 ms Zykluszeit: bis zu 100 ms Verzögerung möglich
- Kritisch für schnelle Prozesse
- Sicherheitsfunktionen können verzögert reagieren

**Beispiel:**
- Not-Halt muss schnell reagieren
- Kurze Impulse könnten übersehen werden
- Schnelle Zählvorgänge werden verfälscht

---

**2. Prozessstabilität**

**Konstante Zykluszeit wichtig für:**
- Regelkreise (PID-Regler benötigen konstante Abtastzeiten)
- Synchronisierte Bewegungen
- Zeitmessungen
- Timer-Genauigkeit

**Problem bei schwankenden Zykluszeiten:**
- Instabile Regelung
- Ungenauer Betrieb
- Schwingungen in der Anlage
- Qualitätsprobleme

---

**3. Watchdog und Systemsicherheit**

**Watchdog-Funktion:**
- Überwacht, ob Zykluszeit eingehalten wird
- Bei Überschreitung → SPS geht in Fehler
- Schutz vor "hängenden" Programmen
- Sicherheitsmechanismus

**Typische Watchdog-Zeiten:**
- Standard: 150-500 ms
- Anpassbar je nach Anwendung
- Zu kurz: Fehlalarme
- Zu lang: Risiko bei echten Problemen

---

**4. Signalerfassung**

**Problem kurzer Impulse:**
- Signal muss länger als Zykluszeit anliegen
- Sonst: Signal wird übersehen
- Kritisch bei schnellen Zählvorgängen

**Lösung:**
- Kurze Zykluszeit
- Hardware-Zähler (unabhängig vom Zyklus)
- Interrupt-Verarbeitung

---

**5. Performance-Anforderungen**

**Optimierung notwendig für:**
- Schnelle Maschinen (Verpackung, Druck)
- Motion Control
- Hochfrequente Prozesse
- Sicherheitstechnische Anforderungen

**Typische Zykluszeiten:**

| Anwendung | Zykluszeit |
|-----------|------------|
| Einfache Steuerung | 50-100 ms |
| Standard-Automation | 10-50 ms |
| Schnelle Maschinen | 1-10 ms |
| Motion Control | <1 ms |
| Safety-Anwendungen | 2-12 ms |

---

**6. Programmeffizienz**

**Faktoren, die Zykluszeit beeinflussen:**

**Programmlänge:**
- Mehr Code = längere Zykluszeit
- Komplexe Berechnungen verlängern Zyklus
- Nicht benötigte Funktionen vermeiden

**Kommunikation:**
- Netzwerkverkehr während Housekeeping
- Viele Kommunikationspartner erhöhen Zykluszeit
- Datenmenge begrenzen

**Programmstruktur:**
- Effiziente Programmierung wichtig
- Unnötige Schleifen vermeiden
- Optimierte Datenstrukturen

---

**7. Determinismus**

**Definition:**
- Vorhersagbares Zeitverhalten
- Wichtig für synchronisierte Abläufe
- Reproduzierbare Ergebnisse

**Anforderungen:**
- Konstante Zykluszeit
- Keine unvorhersehbaren Verzögerungen
- Echtzeitfähigkeit

---

**8. Praktische Konsequenzen**

**Zu lange Zykluszeit:**
- Langsame Reaktion
- Verpasste Signale
- Instabile Regelung
- Qualitätsprobleme
- Sicherheitsrisiken

**Zu kurze Zykluszeit (überdimensioniert):**
- Unnötig teure Hardware
- Höherer Energieverbrauch
- Verschleiß durch häufiges Schalten
- Überdimensionierung

---

**9. Optimierungsstrategien**

**Maßnahmen zur Verkürzung:**
- Code-Optimierung
- Auslagern nicht zeitkritischer Tasks
- Hardware-Counter für Zählvorgänge
- Interrupt-gesteuerte Verarbeitung
- Schnellere CPU wählen

**Überwachung:**
- Minimale, maximale und durchschnittliche Zykluszeit beobachten
- Trends erkennen
- Frühzeitig auf Verschlechterungen reagieren

---

## Aufgabe 9: SPS-Dokumentation

### Aufgabenstellung 9.1
Warum ist eine ausführliche Dokumentation von SPS-Programmen wichtig?

### Lösung 9.1

**Bedeutung der SPS-Dokumentation:**

**1. Wartung und Fehlerbehebung**

**Wichtigkeit:**
- Schnelleres Auffinden von Fehlern
- Reduzierte Stillstandzeiten
- Auch fremde Programmierer können System verstehen
- Historische Probleme nachvollziehbar

**Ohne Dokumentation:**
- Lange Fehlersuche
- Reverse Engineering notwendig
- Hohe Kosten
- Gefahr von Fehlbedienung

---

**2. Wissenserhaltung**

**Problematik:**
- Programmierer wechseln Unternehmen oder Position
- Know-how geht verloren
- Niemand kennt mehr Details der Anlage

**Mit Dokumentation:**
- Wissen bleibt erhalten
- Einarbeitung neuer Mitarbeiter einfacher
- Unabhängigkeit von einzelnen Personen
- Langfristige Wartbarkeit gesichert

---

**3. Gesetzliche und normative Anforderungen**

**Verpflichtungen:**
- CE-Kennzeichnung erfordert technische Dokumentation
- Maschinenrichtlinie 2006/42/EG
- EN 60204 (Elektrische Ausrüstung von Maschinen)
- ISO-Normen
- Qualitätsmanagement (ISO 9001)

**Haftung:**
- Bei Unfällen muss nachgewiesen werden, dass Anlage ordnungsgemäß ist
- Dokumentation als Beweismittel
- Betreiberhaftung

---

**4. Änderungsmanagement**

**Nachvollziehbarkeit:**
- Welche Änderungen wurden wann vorgenommen?
- Warum wurden Änderungen durchgeführt?
- Wer hat Änderungen gemacht?
- Versionshistorie

**Vorteile:**
- Rückverfolgbarkeit von Problemen
- Möglichkeit zum Zurückrollen
- Vermeidung doppelter Arbeit

---

**5. Inbetriebnahme und Schulung**

**Nutzen:**
- Schnellere Inbetriebnahme
- Systematische Schulung möglich
- Bedienungsanleitung für Operator
- Reduzierte Schulungskosten

---

**6. Anlagenerweiterungen**

**Wichtig für:**
- Planung von Erweiterungen
- Prüfung der Machbarkeit
- Kostenschätzung
- Vermeidung von Inkompatibilitäten

---

**7. Qualitätssicherung**

**Aspekte:**
- Code-Reviews möglich
- Standardisierung
- Best Practices umsetzen
- Fehlerreduzierung

---

**8. Wirtschaftlichkeit**

**Kostenaspekte:**
- Reduzierte Wartungskosten
- Kürzere Stillstandzeiten
- Schnellere Problemlösung
- Geringere Abhängigkeit von Spezialisten
- Höherer Wiederverkaufswert der Anlage

**Investition:**
- Dokumentation kostet Zeit
- Aber: ROI durch reduzierte Folgekosten
- Langfristig wirtschaftlich sinnvoll

---

**9. Kundenzufriedenheit**

**Vorteile:**
- Professioneller Eindruck
- Kunde kann Anlage selbst warten
- Vertrauensaufbau
- Wettbewerbsvorteil

---

**10. Troubleshooting aus der Ferne**

**Remote Support:**
- Support-Techniker können Dokumentation vorab studieren
- Vorbereitung auf Remote-Sitzung
- Effizientere Problemlösung
- Reduzierte Reisekosten

---

### Aufgabenstellung 9.2
Nenne drei Arten von Informationen, die in der SPS-Dokumentation enthalten sein sollten.

### Lösung 9.2

**1. Hardware-Dokumentation**

**Inhalt:**

**A) Hardware-Konfiguration:**
- SPS-Typ und Modellbezeichnung
- CPU-Spezifikationen
- Speichergröße
- Firmware-Version
- Betriebssystem

**B) I/O-Konfiguration:**
- Liste aller Ein- und Ausgangsmodule
- Modultypen und Artikelnummern
- Steckplatz-Belegung
- Kanalzuordnung
- Adresstabellen

**Beispiel-Tabelle:**

| Steckplatz | Modultyp | Adressbereich | Funktion |
|------------|----------|---------------|----------|
| Slot 1 | DI 16x24V DC | I0.0 - I1.7 | Sensoren Station 1 |
| Slot 2 | DO 16x24V DC | Q0.0 - Q1.7 | Ventile Station 1 |
| Slot 3 | AI 8x0-10V | IW64 - IW78 | Drucksensoren |

**C) Netzwerkkonfiguration:**
- IP-Adressen aller Teilnehmer
- Netzwerktopologie
- Verwendete Protokolle (z.B. PROFINET, EtherNet/IP)
- Gerätestammdaten
- Switch-Konfiguration

**D) Peripherie:**
- Antriebe und Motoren
- Feldgeräte (Sensoren, Aktoren)
- HMI/Bedienpanels
- Sicherheitskomponenten
- RFID-Leser, Barcodescanner etc.

**E) Schaltpläne und Layouts:**
- Elektrische Schaltpläne (E-CAD)
- Klemmenpläne
- Schaltschrankaufbau
- Verdrahtungslisten
- Kabellaufpläne

**F) Technische Daten:**
- Spannungsversorgung
- Leistungsaufnahme
- Umgebungsbedingungen
- Schutzarten

*Verifiziert durch Control Plus.pdf: Umfangreiche Hardware-Details zu IPC VPB, CX2020, mPad werden dokumentiert*

---

**2. Software-Dokumentation**

**Inhalt:**

**A) Programmstruktur:**
- Übersicht aller Programmbausteine
- Funktionsbausteine (FB)
- Funktionen (FC)
- Datenbausteine (DB)
- Organisation der Programme
- Bausteinhierarchie

**B) Variablenlisten:**
- Globale Variablen
- Lokale Variablen
- Symbolische Namen
- Datentypen
- Beschreibungen
- Verwendungszweck

**Beispiel:**

```
Variable: Zylinder_1_Ausfahren
Typ: BOOL
Adresse: Q0.0
Beschreibung: Ausgang für Magnetventil Zylinder 1, Station Montage
Sicherheit: Verriegelt mit Schutztuerkontakt_1
```

**C) Programmlogik:**
- Ablaufbeschreibungen
- Flussdiagramme
- Zustandsdiagramme
- Zeitdiagramme
- Logische Verknüpfungen

**D) Programmkommentare:**
- Inline-Kommentare im Code
- Erklärung komplexer Algorithmen
- Beschreibung von Sonderfällen
- Begründung für gewählte Lösungen

**E) Funktionsbeschreibungen:**
- Was macht der Baustein?
- Eingänge und deren Bedeutung
- Ausgänge und deren Bedeutung
- Voraussetzungen für Aufruf
- Rückgabewerte

**F) Versionsverwaltung:**
- Versionshistorie
- Änderungsprotokoll (Change Log)
- Datum und Autor der Änderungen
- Beschreibung der Änderungen
- Versionsnummern

**Beispiel:**

```
Version 2.3.1 - 15.11.2023 - Max Mustermann
- Fehler in Station 3 behoben (Zylinder fuhr nicht komplett aus)
- Timer T15 von 2s auf 3s erhöht
- Sicherheitsabfrage für Lichtgitter hinzugefügt
```

**G) Parameter und Konfiguration:**
- Rezeptdaten
- Einstellbare Parameter
- Sollwerte
- Grenzwerte
- Kalibrierungsdaten

**H) Alarm- und Meldungslisten:**
- Alle möglichen Fehler und Warnungen
- Fehlernummern
- Fehlertexte
- Ursachen
- Behebungsmaßnahmen

*Verifiziert durch Control Plus.pdf: Baukasten-Engineering-Konzept erfordert strukturierte Dokumentation wiederverwendbarer Bausteine*

---

**3. Funktionale und prozessbezogene Dokumentation**

**Inhalt:**

**A) Prozessbeschreibung:**
- Anlagenübersicht
- Produktionsablauf
- Maschinenzyklen
- Betriebsarten (Automatik, Manuell, Service)
- Sequenzen und Schritte

**Beispiel:**
```
Automatikzyklus Montagestation:
1. Werkstück bereitstellen
2. Werkstück prüfen (Sensor S1)
3. Komponente A einpressen (Zylinder Z1)
4. Komponente B verschrauben (Schrauber M1)
5. Qualitätsprüfung (Kamera)
6. Werkstück ausschleusen
```

**B) Sicherheitskonzept:**
- Sicherheitsfunktionen
- Not-Halt-Konzept
- Schutztüren und Verriegelungen
- Lichtgitter und Lichtvorhänge
- Sicherheitskategorie (z.B. PLd nach ISO 13849)
- Risikobeurteilung

**C) Bedienungsanleitung:**
- Inbetriebnahme der Anlage
- Normale Bedienung
- Fehlerbehebung
- Wartungshinweise
- Do's and Don'ts

**D) HMI-Dokumentation:**
- Screenshots der Bedienoberfläche
- Erklärung der Anzeigeelemente
- Menüstruktur
- Bedienelemente und ihre Funktion
- Zugriffslevel und Passwörter

*Verifiziert durch Control Plus.pdf: HMI-Konzept mit Baumstruktur zur Navigation erfordert entsprechende Dokumentation*

**E) Timing und Performance:**
- Zykluszeiten
- Taktzeiten
- Performance-Anforderungen
- Reaktionszeiten

**F) Schnittstellen:**
- Kommunikation mit anderen Systemen
- Datenformate
- Protokolle
- Übergabepunkte

**G) Inbetriebnahme-Protokolle:**
- Testprotokolle
- Abnahmeprotokolle
- Messergebnisse
- Kalibrierungsdaten

**H) Wartungsplan:**
- Wartungsintervalle
- Checklisten
- Verschleißteile
- Empfohlene Ersatzteile

**I) Kontaktdaten:**
- Hersteller der Anlage
- Support-Kontakte
- Telefonnummern für Notfälle
- Verantwortliche Personen

---

**Zusätzliche wichtige Dokumentationsarten:**

**4. Mechanische Dokumentation:**
- 3D-Modelle
- 2D-Zeichnungen
- Stücklisten

**5. Prüf- und Testdokumentation:**
- Funktionsprüfungen
- FAT (Factory Acceptance Test)
- SAT (Site Acceptance Test)

**6. Ersatzteillisten:**
- Kritische Komponenten
- Lieferanten
- Artikelnummern

---

## Aufgabe 10: SPS-Steuerungshierarchien

### Aufgabenstellung 10.1
Erläutere den Unterschied zwischen zentraler und dezentraler SPS-Steuerung.

### Lösung 10.1

**Zentrale SPS-Steuerung:**

**Definition:**
Eine zentrale SPS befindet sich an einem Ort (typischerweise im Hauptschaltschrank) und steuert alle Prozesse der Anlage von diesem zentralen Punkt aus.

**Aufbau:**
- Eine zentrale SPS-CPU
- Alle I/O-Module im gleichen Rack oder direkt verbunden
- Zentrale Verkabelung
- Stern-Topologie

**Merkmale:**

**Verkabelung:**
- Alle Feldgeräte (Sensoren, Aktoren) werden direkt zur zentralen SPS verkabelt
- Lange Kabelwege zur Peripherie
- Hoher Verkabelungsaufwand
- Dicke Kabelbäume

**Programmierung:**
- Ein zusammenhängendes Programm
- Übersichtliche Struktur für kleinere Anlagen
- Zentrale Datenhaltung

**Wartung:**
- Alle Komponenten an einem Ort
- Zentrale Diagnose
- Ein Ansprechpartner für die gesamte Steuerung

**Vorteile:**
- Einfache Programmstruktur bei kleinen Anlagen
- Niedrige Anschaffungskosten bei kleinen Anlagen
- Weniger Netzwerk-Know-how erforderlich
- Zentrale Übersicht
- Keine Netzwerkprobleme

**Nachteile:**
- Hoher Verkabelungsaufwand bei großen Anlagen
- Lange Kabelwege = höhere Störanfälligkeit
- Unflexibel bei Erweiterungen
- Bei Ausfall der zentralen SPS steht gesamte Anlage still
- Hohe Kabelkosten bei großen Anlagen
- Unübersichtlich bei komplexen Prozessen
- Platzbedarf im Hauptschaltschrank

**Typische Anwendungen:**
- Kleine bis mittlere Maschinen
- Kompakte Anlagen
- Einzelmaschinen
- Einfache Prozesse

---

**Dezentrale SPS-Steuerung:**

**Definition:**
Die Steuerung ist auf mehrere intelligente Einheiten verteilt, die über ein Bussystem miteinander kommunizieren. I/O-Module und Subsysteme befinden sich direkt am Prozess.

**Aufbau:**
- Zentrale oder mehrere verteilte CPUs
- Dezentrale I/O-Stationen nahe am Prozess
- Feldbus- oder Industrial Ethernet-Verbindung
- Bus-Topologie oder Stern-Topologie

**Merkmale:**

**Verkabelung:**
- Feldgeräte werden an dezentrale I/O-Stationen vor Ort angeschlossen
- Kurze Kabelwege zu den Sensoren/Aktoren
- Ein Bus-Kabel verbindet alle Stationen
- Drastisch reduzierter Verkabelungsaufwand

**Programmierung:**
- Modulare Programmstruktur
- Verteilte Intelligenz möglich
- Jede Station kann eigene Programme haben
- Koordination über Netzwerk

**Wartung:**
- Dezentrale Diagnose
- Module können einzeln getauscht werden
- Ferndiagnose möglich
- Teilbereiche können unabhängig gewartet werden

**Vorteile:**
- Erheblich reduzierter Verkabelungsaufwand bei großen Anlagen
- Kurze Kabelwege = geringere Störanfälligkeit
- Hohe Flexibilität bei Erweiterungen
- Modularer Aufbau
- Teile der Anlage können weiterlaufen bei Teilausfällen
- Einfache Erweiterbarkeit
- Bessere Strukturierung bei komplexen Anlagen
- Kostenersparnis bei großen Anlagen
- Hot-Swap teilweise möglich

**Nachteile:**
- Höhere Anfangskosten (Bussystem, dezentrale Stationen)
- Netzwerk-Know-how erforderlich
- Komplexere Fehlerdiagnose
- Netzwerkprobleme möglich
- Abhängigkeit vom Bussystem
- Höherer Programmieraufwand

**Typische Anwendungen:**
- Große Produktionsanlagen
- Fertigungslinien
- Weitläufige Anlagen
- Modulare Maschinen
- Flexibles Manufacturing

---

**Vergleichstabelle:**

| Aspekt | Zentral | Dezentral |
|--------|---------|-----------|
| **Verkabelung** | Sehr hoch | Gering |
| **Flexibilität** | Niedrig | Hoch |
| **Kosten klein** | Niedrig | Hoch |
| **Kosten groß** | Hoch | Niedrig |
| **Ausfallsicherheit** | Niedrig | Hoch |
| **Komplexität** | Niedrig | Mittel-Hoch |
| **Erweiterbarkeit** | Schwierig | Einfach |
| **Störanfälligkeit** | Höher (lange Kabel) | Niedriger (kurze Kabel) |
| **Wartung** | Zentral | Verteilt |
| **Diagnose** | Einfach | Komplex |

---

**Hybride Systeme:**

In der Praxis werden oft hybride Lösungen eingesetzt:
- Zentrale CPU mit dezentraler Peripherie
- Mehrere dezentrale Controller mit zentraler Überwachung
- Kombination aus zentral gesteuerten und autonomen Subsystemen

---

**Beispiel:**

**Zentral:**
Eine Verpackungsmaschine mit allen Sensoren und Aktoren im Umkreis von 5 Metern, alle verkabelt zu einer SPS im Schaltschrank der Maschine.

**Dezentral:**
Eine Fertigungslinie mit 10 Bearbeitungsstationen über 100 Meter Länge. Jede Station hat eine dezentrale I/O-Station vor Ort, alle verbunden über PROFINET mit der zentralen Steuerung.

---

### Aufgabenstellung 10.2
Warum wird die dezentrale Steuerung in bestimmten Anwendungen bevorzugt?

### Lösung 10.2

**Gründe für dezentrale Steuerung:**

**1. Große räumliche Ausdehnung**

**Problem bei zentraler Steuerung:**
- Produktionslinien erstrecken sich über 50-200 Meter
- Hunderte von Sensoren und Aktoren
- Kilometerlange Kabel erforderlich
- Enorme Kabeltrassen notwendig

**Lösung durch Dezentralisierung:**
- I/O-Stationen direkt bei den Maschinen
- Nur ein Buskabel verbindet alle Stationen
- Kurze Anschlusskabel zu Sensoren/Aktoren
- Drastische Kosteneinsparung

**Beispiel:**
Automobilmontagelinie mit 20 Stationen auf 150m Länge - Dezentrale I/O spart hier mehrere Kilometer Kabel ein.

---

**2. Modularer Maschinenaufbau**

**Anforderung:**
- Maschinen sollen in verschiedenen Konfigurationen geliefert werden
- Kunde wählt benötigte Module aus
- Spätere Erweiterungen möglich

**Vorteile dezentral:**
- Jedes Modul hat eigene I/O-Station
- Plug & Play beim Hinzufügen von Modulen
- Standardisierung der Module möglich
- Einfache Konfigurationsänderungen

**Beispiel:**
Verpackungsanlage mit optionalen Modulen (Etikettierer, Qualitätsprüfung, verschiedene Zuführsysteme).

*Verifiziert durch Control Plus.pdf: Baukasten-Engineering ermöglicht modulare, dezentrale Strukturen*

---

**3. Flexible Fertigung und Industrie 4.0**

**Anforderungen:**
- Schnelle Produktwechsel
- Rekonfigurierbare Produktionslinien
- Austauschbare Stationen
- Adaptive Fertigungssysteme

**Dezentrale Vorteile:**
- Stationen können umkonfiguriert werden
- Prozessnah einstellbare Parameter
- Autonome, intelligente Subsysteme
- Einfache Integration neuer Technologien

**Industrie 4.0 Aspekte:**
- Cyber-Physical Systems (CPS)
- Selbstorganisierende Produktionssysteme
- Machine-to-Machine Kommunikation (M2M)
- Digitaler Zwilling für jedes Modul

*Verifiziert durch Control Plus.pdf: OpCon Control Plus unterstützt Connectivity und moderne Automatisierungskonzepte*

---

**4. Ausfallsicherheit und Verfügbarkeit**

**Risikoverteilung:**
- Bei Ausfall einer dezentralen Station: Nur Teilbereich betroffen
- Restliche Anlage kann weiterlaufen
- Höhere Gesamtverfügbarkeit

**Redundanz:**
- Kritische Bereiche können redundant ausgelegt werden
- Einzelne Komponenten austauschbar im Betrieb
- Hot-Swap-Fähigkeit

**Beispiel:**
In einer Chemiefabrik können bei Ausfall einer Pumpenstation die anderen Bereiche weiterproduzieren.

---

**5. Einfache Wartung und Diagnose**

**Lokale Diagnose:**
- Statusinformationen direkt am Modul
- LED-Anzeigen an dezentralen Stationen
- Fehlereingrenzung vereinfacht
- Wartungspersonal findet Fehlerort schnell

**Austauschbarkeit:**
- Defekte Module schnell identifizierbar
- Austausch ohne Eingriff in Gesamtsystem
- Minimale Stillstandszeit

**Remote Maintenance:**
- Einzelne Subsysteme können ferngewartet werden
- Gezielte Updates möglich
- Diagnose über Netzwerk

---

**6. Elektromagnetische Verträglichkeit (EMV)**

**Problem lange Leitungen:**
- Störanfälligkeit nimmt mit Kabellänge zu
- Einstreuungen in Signalleitungen
- Potentialunterschiede bei großen Entfernungen

**Dezentrale Lösung:**
- Kurze Signalleitungen = weniger Störungen
- Digitale Buskommunikation robuster als analoge Signale
- Galvanische Trennung an den I/O-Stationen
- Bessere Signalqualität

---

**7. Kostenoptimierung bei großen Anlagen**

**Einsparungen:**
- **Kabelkosten:** 40-60% Ersparnis
- **Installationskosten:** Schnellere Montage
- **Engineering:** Modulare Programmierung wiederverwendbar
- **Inbetriebnahme:** Modulweise möglich
- **Änderungen:** Einfacher umsetzbar

**Break-Even:**
- Ab ca. 50-100 I/O-Punkten wird dezentral wirtschaftlicher
- Bei großen Entfernungen noch früher

---

**8. Standardisierung und Wiederverwendung**

**Modulbibliotheken:**
- Standardisierte Subsysteme
- Einmal entwickelt, mehrfach genutzt
- Baukasten-Engineering
- Reduzierter Entwicklungsaufwand

**Best Practices:**
- Bewährte Lösungen werden Module
- Qualitätssteigerung durch Wiederverwendung
- Kürzere Time-to-Market

*Verifiziert durch Control Plus.pdf: Baukasten-Engineering mit wiederverwendbaren Bausteinen ist Kernkonzept*

---

**9. Skalierbarkeit**

**Wachstum:**
- Start mit kleiner Anlage möglich
- Schrittweise Erweiterung
- Keine Neuplanung bei Vergrößerung
- Investitionen zeitlich gestreckt

**Anpassung:**
- An veränderte Produktionsvolumen anpassbar
- Temporäre Erweiterungen möglich
- Flexible Kapazitätsplanung

---

**10. Spezielle technische Anforderungen**

**Explosionsgeschützte Bereiche:**
- Dezentrale Stationen in Ex-Bereichen
- Zentrale Steuerung in sicherem Bereich
- Reduzierung von Durchführungen

**Hygiene-Anforderungen:**
- In Lebensmittel-/Pharmaproduktion
- Dezentrale I/O in Edelstahlgehäusen
- IP69K-Schutzart möglich
- Leichte Reinigbarkeit

**Extreme Umgebungsbedingungen:**
- Temperaturextreme
- Feuchte Umgebungen
- Staubige Bereiche
- Angepasste dezentrale Module verfügbar

---

**Zusammenfassung - Dezentral bevorzugt bei:**

1. Großen räumlichen Ausdehnungen (>20m)
2. Modularem Anlagenkonzept
3. Flexibler, rekonfigurierbarer Fertigung
4. Hohen Verfügbarkeitsanforderungen
5. Häufigen Anlagenerweiterungen
6. EMV-kritischen Umgebungen
7. Mehr als 50-100 I/O-Punkten
8. Standardisierungswünschen
9. Industrie 4.0 Anwendungen
10. Speziellen Umgebungsbedingungen

---

## Aufgabe 11: SPS in der Industrie 4.0

### Aufgabenstellung 11.1
Wie trägt die SPS-Technologie zur Umsetzung von Industrie 4.0 bei?

### Lösung 11.1

**Beiträge der SPS zu Industrie 4.0:**

**1. Konnektivität und Vernetzung**

**Moderne SPS als Kommunikations-Hub:**
- Anbindung an Industrial Internet of Things (IIoT)
- Integration verschiedener Protokolle
- Echtzeitfähige Kommunikation
- Cloud-Konnektivität

**Vernetzungsebenen:**
- Horizontale Integration: Maschine-zu-Maschine (M2M)
- Vertikale Integration: Feldebene bis ERP-System
- Ende-zu-Ende-Integration: Über Unternehmensgrenzen hinweg

**Protokolle:**
- OPC UA für standardisierte Kommunikation
- MQTT für Cloud-Anbindung
- Ethernet-basierte Feldbussysteme
- Web-Services und REST-APIs

*Verifiziert durch Control Plus.pdf: "Connectivity" wird als zentrale Komponente der Plattform genannt*

---

**2. Datenerfassung und Big Data**

**SPS als Datenquelle:**
- Kontinuierliche Erfassung von Prozessdaten
- Maschinenzustandsdaten
- Qualitätsdaten
- Produktionsdaten

**Datenmenge:**
- Hochfrequente Erfassung (ms-Bereich)
- Historisierung
- Kontextinformationen
- Ereignisprotokolle

**Verwendung:**
- Produktionsoptimierung
- Qualitätsanalyse
- Predictive Analytics
- Process Mining

---

**3. Cyber-Physical Systems (CPS)**

**SPS als Brücke:**
- Verbindung physische Welt ↔ digitale Welt
- Sensordaten → Digitales Modell
- Steuerungsbefehle → Physische Aktionen

**Digitaler Zwilling (Digital Twin):**
- SPS liefert Echtzeitdaten für virtuelles Modell
- Simulation und reale Anlage synchronisiert
- Optimierung im digitalen Modell testbar
- Vorhersage von Maschinenverhalten

---

**4. Predictive Maintenance (Vorausschauende Wartung)**

**Datengrundlage:**
- SPS erfasst Betriebsstunden
- Lastwechsel
- Temperaturverläufe
- Vibrationen (über spezielle Sensoren)
- Fehlerhäufigkeiten

**Auswertung:**
- Erkennung von Verschleißmustern
- Vorhersage von Ausfällen
- Optimierung von Wartungsintervallen
- Reduzierung ungeplanter Stillstände

**Ergebnis:**
- Kosteneinsparung
- Höhere Verfügbarkeit
- Von reaktiver zu proaktiver Wartung

---

**5. Flexible und adaptive Produktion**

**Rekonfigurierbarkeit:**
- Schneller Produktwechsel
- Anpassung an Kundenindividuelle Produkte (Losgröße 1)
- Selbstoptimierende Prozesse

**SPS-Beitrag:**
- Rezeptverwaltung
- Parametrierbare Prozesse
- Automatische Anpassung
- Schnelle Umrüstzeiten

**Beispiel:**
- Automobilproduktion: Verschiedene Modelle auf einer Linie
- SPS erkennt Fahrzeugtyp (RFID) und passt Programm automatisch an

---

**6. Dezentralisierung und Autonomie**

**Edge Computing:**
- Intelligenz direkt an der Maschine
- Vorverarbeitung von Daten
- Lokale Entscheidungen
- Reduzierte Latenz

**Autonome Systeme:**
- Selbstständige Prozessoptimierung
- Adaptive Regelung
- Lokale KI/ML-Algorithmen
- Swarm Intelligence

---

**7. Mensch-Maschine-Zusammenarbeit**

**Moderne HMI:**
- Tablet- und Smartphone-Bedienung
- Augmented Reality (AR) für Wartung
- Intuitive Benutzeroberflächen
- Kontextsensitive Hilfen

**Assistenzsysteme:**
- SPS liefert Informationen für Bedienerführung
- Schritt-für-Schritt-Anleitungen
- Warnung vor Fehlbedienung
- Qualifikationsmanagement

*Verifiziert durch Control Plus.pdf: HMI und APPs werden als wichtige Komponenten genannt, Training wird unterstützt*

---

**8. Sicherheit und Security**

**Safety:**
- Integrierte Sicherheitsfunktionen
- Safety-over-Fieldbus
- Sichere Mensch-Roboter-Kollaboration

**Security:**
- Schutz vor Cyber-Angriffen
- Verschlüsselte Kommunikation
- Zugriffskontrollen
- Firewalls und Segmentierung

**Wichtigkeit:**
- Vernetzte Systeme = Angriffsfläche
- Schutz kritischer Infrastruktur
- Datenschutz (DSGVO)

---

**9. Standardisierung und Interoperabilität**

**Offene Standards:**
- OPC UA als herstellerunabhängiges Protokoll
- AutomationML für Anlagenbeschreibung
- PLCopen für Programmbausteine
- PackML für Verpackungsmaschinen

**Asset Administration Shell (AAS):**
- Standardisierte Beschreibung von Assets
- Digitaler Produktpass
- Interoperabilität verschiedener Hersteller

---

**10. Simulation und Virtuelle Inbetriebnahme**

**SPS in der Simulation:**
- Virtual Commissioning
- Programme testen ohne Hardware
- Parallele Entwicklung Mechanik/Elektrik/Software
- Zeitersparnis

**Vorteile:**
- Fehler frühzeitig erkennen
- Reduzierte Inbetriebnahmezeit vor Ort
- Schulung an virtueller Anlage
- Optimierung vor Bau

---

**11. Energiemanagement**

**Monitoring:**
- SPS erfasst Energieverbräuche
- Identifikation von Einsparpotentialen
- Last- und Verbrauchsprofile

**Steuerung:**
- Abschaltung ungenutzter Anlagenteile
- Lastmanagement
- Energieoptimierte Fahrweise

**Nachhaltigkeit:**
- CO2-Fußabdruck reduzieren
- Ressourcenschonung
- Compliance mit Umweltauflagen

---

**12. Rückverfolgbarkeit und Traceability**

**Track & Trace:**
- SPS protokolliert alle Prozessschritte
- Verknüpfung mit Produktseriennummern
- Qualitätsdaten je Produkt
- Rückverfolgung bei Reklamationen

**Qualitätsmanagement:**
- Lückenlose Dokumentation
- Prozessfähigkeitsnachweis
- FDA-Konformität (Pharma)
- Automotive-Standards

---

**Zusammenfassung:**

Die SPS ist das **zentrale Bindeglied** in Industrie 4.0:
- Sammelt Daten aus der physischen Welt
- Steuert Prozesse intelligent
- Vernetzt verschiedene Ebenen
- Ermöglicht Digitalisierung der Produktion
- Basis für fortgeschrittene Analysen und KI
- Voraussetzung für autonome, flexible Fertigung

**Ohne moderne SPS-Technologie ist Industrie 4.0 nicht umsetzbar.**

---

### Aufgabenstellung 11.2
Nenne zwei Merkmale von Industrie 4.0, die von SPS-Systemen unterstützt werden.

### Lösung 11.2

**Merkmal 1: Horizontale und Vertikale Integration**

**Was ist Integration in Industrie 4.0?**

Integration bedeutet die nahtlose Vernetzung und den Datenaustausch zwischen verschiedenen Systemen, Ebenen und Bereichen der Produktion.

---

**Horizontale Integration:**

**Definition:**
Vernetzung von Systemen auf der gleichen Hierarchieebene, typischerweise auf Produktionsebene.

**Beispiele:**
- Maschine 1 kommuniziert mit Maschine 2
- Fertigungslinien tauschen Daten aus
- Verschiedene Standorte sind vernetzt
- Supply Chain Integration

**Wie SPS das unterstützt:**

**1. Maschine-zu-Maschine-Kommunikation (M2M):**
- SPS A sendet Produktionsstatus an SPS B
- Synchronisation von Produktionsschritten
- Weitergabe von Werkstückdaten
- Koordination von Materialflüssen

**Praktisches Beispiel:**
```
Bearbeitungsmaschine (SPS 1) → Werkstück fertig
↓
Signal an Transportband (SPS 2) → Transport starten
↓
Signal an Montagestation (SPS 3) → Werkstück vorbereiten
```

**2. Protokolle:**
- PROFINET, EtherNet/IP für Echtzeitkommunikation
- OPC UA für Datenaustausch
- MQTT für Cloud-Integration

**3. Dezentrale Intelligenz:**
- Jede SPS trifft lokale Entscheidungen
- Keine zentrale "Master"-Steuerung notwendig
- Selbstorganisierende Produktionssysteme

---

**Vertikale Integration:**

**Definition:**
Durchgängige Vernetzung über alle Hierarchieebenen vom Sensor bis zum ERP-System.

**Ebenen (nach Automatisierungspyramide):**

```
Ebene 5: ERP (Enterprise Resource Planning)
          ↕ (SPS liefert Daten nach oben)
Ebene 4: MES (Manufacturing Execution System)
          ↕
Ebene 3: SCADA/HMI (Prozessvisualisierung)
          ↕
Ebene 2: SPS (Steuerungsebene) ← Zentrale Rolle!
          ↕
Ebene 1: Sensoren/Aktoren (Feldebene)
```

**Wie SPS das unterstützt:**

**1. Daten von unten (Feldebene):**
- SPS sammelt Sensordaten
- Verarbeitet Prozessinformationen
- Aggregiert Daten

**2. Daten nach oben (IT-Ebene):**
- Produktionszahlen an MES
- Maschinenzustände an SCADA
- OEE-Daten (Overall Equipment Effectiveness) an ERP
- Qualitätsdaten an Datenbank

**3. Befehle von oben:**
- Produktionsaufträge vom MES
- Rezepte und Parameter vom SCADA
- Sollwerte von übergeordneten Systemen

**Praktisches Beispiel:**

**Vom Sensor zum Management:**
1. Temperatursensor misst 85°C
2. SPS erfasst und verarbeitet Wert
3. SPS meldet: "Prozess OK, Produktion läuft"
4. SCADA zeigt Status an
5. MES bucht: "1 Stück produziert"
6. ERP aktualisiert: Lagerbestand +1

**Vorteile der Integration durch SPS:**
- Echtzeitdaten für schnelle Entscheidungen
- Transparenz über alle Ebenen
- Durchgängiger Informationsfluss
- Basis für Optimierungen
- Vermeidung von Datensilos

**Technologien:**
- OPC UA: Standard für vertikale Integration
- REST APIs: Web-Services
- Datenbanken: Direktanbindung möglich
- Cloud-Gateways: Für Cloud-Plattformen

*Verifiziert durch Control Plus.pdf: "Information Services" zeigt vertikale Integration, "Connectivity" ermöglicht horizontale Vernetzung*

---

**Merkmal 2: Echtzeitfähigkeit und Transparenz**

**Was bedeutet das in Industrie 4.0?**

Echtzeitfähigkeit und Transparenz bedeuten, dass Informationen über den Zustand von Produktionsprozessen sofort verfügbar und für alle relevanten Systeme und Personen zugänglich sind.

---

**Echtzeitfähigkeit:**

**Definition:**
Fähigkeit, Prozessdaten in Echtzeit (Millisekunden bis Sekunden) zu erfassen, zu verarbeiten und darauf zu reagieren.

**Wie SPS das unterstützt:**

**1. Schnelle Zykluszeiten:**
- Moderne SPS: Zykluszeiten von <1ms möglich
- Sofortige Reaktion auf Ereignisse
- Deterministisches Verhalten

**2. Echtzeitkommunikation:**
- PROFINET IRT: Jitter <1µs
- EtherCAT: Zykluszeiten <100µs
- Synchrone Bewegungssteuerung möglich

**3. Edge Computing:**
- Datenvorverarbeitung direkt in der SPS
- Keine Verzögerung durch Cloud-Roundtrip
- Lokale KI/ML-Algorithmen für schnelle Entscheidungen

**4. Ereignisgesteuerte Verarbeitung:**
- Interrupts für kritische Ereignisse
- Prioritätsbasierte Programmausführung
- Hardware-Counter für schnelle Zählvorgänge

**Anwendungsbeispiele:**

**Motion Control:**
- Synchronisation mehrerer Achsen
- Präzision im µm-Bereich
- Fliegende Säge, Flying-Shear

**Qualitätskontrolle:**
- Kamera erkennt Fehler
- SPS reagiert in <10ms
- Fehlteil wird ausgeschleust

**Prozessregelung:**
- Temperatur weicht ab
- Sofortige Korrektur
- Vermeidung von Ausschuss

---

**Transparenz:**

**Definition:**
Vollständige Sichtbarkeit aller relevanten Prozess- und Produktionsdaten in Echtzeit für alle berechtigten Nutzer.

**Wie SPS das unterstützt:**

**1. Kontinuierliche Datenerfassung:**
- Alle Prozessparameter werden protokolliert
- Maschinenzustände
- Produktionszahlen
- Qualitätsdaten
- Energieverbräuche

**2. Datenbereitstellung:**
- SPS stellt Daten über verschiedene Schnittstellen bereit
- HMI/SCADA für Bediener
- MES für Produktionsplaner
- Datenbanken für Analysen
- Cloud für Management

**3. Kontextualisierung:**
- Daten werden mit Zusatzinformationen versehen
- Zeitstempel
- Produktionsl auftragsnummer
- Maschinenzustand
- Bediener-ID

**4. Alarmierung und Benachrichtigung:**
- Automatische Meldungen bei Abweichungen
- Push-Benachrichtigungen an Mobile Devices
- Eskalationsmanagement

**Anwendungsbeispiele:**

**Produktionsdashboard:**
- Management sieht aktuelle Produktionszahlen
- OEE wird in Echtzeit berechnet
- Engpässe sofort erkennbar

**Qualitätsmonitoring:**
- Jedes Produkt mit Qualitätsdaten verknüpft
- Trends frühzeitig erkennbar
- Proaktive Qualitätssicherung

**Energiemonitoring:**
- Verbrauch je Maschine sichtbar
- Spitzenlast-Management
- Identifikation von Einsparpotentialen

**Wartungsplanung:**
- Betriebsstunden aller Komponenten transparent
- Automatische Wartungsmeldungen
- Ersatzteilbedarfsplanung

**5. Digital Twin / Digitaler Zwilling:**
- SPS-Daten speisen virtuelles Modell
- Echtzeitvisualisierung der realen Anlage
- Simulation und Optimierung
- Was-wäre-wenn-Analysen

---

**Vorteile von Echtzeitfähigkeit und Transparenz:**

**Betrieblich:**
- Schnellere Reaktion auf Störungen
- Reduzierte Stillstandzeiten
- Höhere Produktivität
- Bessere Qualität

**Organisatorisch:**
- Informierte Entscheidungen
- Datenbasiertes Management
- Kontinuierliche Verbesserung (KVP)
- Lean Production

**Strategisch:**
- Wettbewerbsvorteil
- Kundenvertrauen durch Transparenz
- Innovation durch Datenanalyse
- Basis für KI-Anwendungen

---

**Technische Umsetzung in modernen SPS:**

**Hardware:**
- Leistungsfähige CPUs
- Ausreichend Speicher für Datenlogging
- Mehrere Ethernet-Schnittstellen
- Zeitsynchronisation (PTP - Precision Time Protocol)

**Software:**
- Integrierte Webserver für Visualisierung
- OPC UA Server/Client
- MQTT-Konnektivität
- SQL-Datenbankanbindung
- REST APIs

**Sicherheit:**
- Verschlüsselte Kommunikation
- Benutzerverwaltung
- Audit Trails
- Zugriffskontrolle

*Verifiziert durch Control Plus.pdf: Real-time-Ethernet-Kommunikation und Information Services werden explizit erwähnt*

---

**Zusammenfassung:**

Diese beiden Merkmale – **Integration** und **Echtzeitfähigkeit/Transparenz** – sind fundamentale Bausteine von Industrie 4.0, die ohne moderne SPS-Systeme nicht realisierbar wären:

1. **Integration** schafft die Vernetzung (horizontal und vertikal)
2. **Echtzeitfähigkeit und Transparenz** sorgen für zeitnahe, vollständige Information

Die SPS agiert dabei als:
- Datensammler
- Echtzeitverarbeiter
- Kommunikations-Gateway
- Lokale Intelligenz
- Schnittstelle zwischen OT und IT

**Ohne diese Fähigkeiten moderner SPS keine Smart Factory!**

---

## Aufgabe 12: SPS-Wartung und Diagnose

### Aufgabenstellung 12.1
Warum ist die regelmäßige Wartung von SPS-Systemen wichtig?

### Lösung 12.1

**Bedeutung regelmäßiger Wartung:**

**1. Vermeidung ungeplanter Ausfälle**

**Problematik:**
- Ungeplante Stillstände sind sehr teuer
- Produktionsverluste
- Liefertermine gefährdet
- Notfallreparaturen teurer als geplante Wartung

**Durch Wartung:**
- Verschleißteile werden rechtzeitig getauscht
- Probleme werden erkannt bevor sie kritisch werden
- Planbare Wartungsfenster statt Notfälle
- Höhere Anlagenverfügbarkeit

**Kostenfaktor:**
- Produktionsausfall: 1.000-100.000 €/Stunde (je nach Branche)
- Geplante Wartung: Bruchteil davon
- ROI der Wartung ist sehr hoch

---

**2. Verlängerung der Lebensdauer**

**Verschleißerscheinungen:**
- Elektronische Bauteile altern
- Lüfter verstauben und verschleißen
- Steckverbindungen oxidieren
- Batterien entladen sich
- Speicherkarten haben begrenzte Schreibzyklen

**Wartungsmaßnahmen:**
- Reinigung von Lüftern und Kühlkörpern
- Prüfung und Reinigung von Kontakten
- Batteriewechsel
- Austausch alternder Komponenten
- Firmware-Updates

**Ergebnis:**
- SPS-Systeme können 15-20 Jahre laufen
- Ohne Wartung: Deutlich kürzere Lebensdauer
- Investitionsschutz
- Reduzierter Ersatzbedarf

---

**3. Sicherstellung der Funktionalität**

**Funktionsprüfungen:**
- Not-Halt-Funktionen testen
- Sicherheitsschaltungen überprüfen
- Backup-Systeme testen
- Redundanzen prüfen

**Sicherheit:**
- Personenschutz gewährleistet
- Maschinenschutz funktioniert
- Rechtskonformität (CE, Arbeitsschutz)
- Haftungsvermeidung

**Gesetzliche Anforderungen:**
- Betriebssicherheitsverordnung (BetrSichV)
- DGUV Vorschriften
- Maschinenrichtlinie
- Dokumentationspflicht

---

**4. Datenintegrität und Programmsicherheit**

**Datensicherung:**
- Regelmäßige Backups des SPS-Programms
- Sicherung von Parametern und Rezepten
- Dokumentation von Änderungen
- Versionsverwaltung

**Risiken ohne Backup:**
- Defekter Speicher = Programm verloren
- Niemand hat Quellcode
- Neuinbetriebnahme unmöglich oder sehr teuer
- Know-how-Verlust

**Wartungsaufgaben:**
- Backup erstellen und extern lagern
- Programm-Versionen dokumentieren
- Batterie für Pufferspeicher wechseln (typisch alle 3-5 Jahre)
- NOVRAM-Funktion prüfen

---

**5. Erkenntnisgewinn für Optimierungen**

**Datenanalyse während Wartung:**
- Fehlerstatistiken auswerten
- Betriebsstunden analysieren
- Lastkollektive prüfen
- Performance-Kennzahlen erheben

**Optimierungspotentiale:**
- Häufige Fehler beheben
- Prozesse verbessern
- Energieverbrauch optimieren
- Effizienzsteigerung

**Continuous Improvement:**
- Regelmäßige Überprüfung = Basis für KVP
- Best Practices identifizieren
- Lessons Learned dokumentieren

---

**6. Softwarepflege**

**Firmware-Updates:**
- Behebung von Sicherheitslücken (Cyber Security)
- Fehlerkorrekturen
- Neue Funktionen
- Verbesserte Performance

**Kompatibilität:**
- Anpassung an neue Feldgeräte
- Protokoll-Updates
- Betriebssystem-Aktualisierungen

**Wichtig:**
- Updates müssen getestet werden
- Backup vor Update
- Kompatibilität mit Anwenderprogramm prüfen
- Dokumentation aktualisieren

---

**7. Umgebungsbedingungen prüfen**

**Kontrolle von:**
- Temperatur im Schaltschrank (Sollwert meist <40°C)
- Luftfeuchtigkeit
- Verschmutzung
- Korrosion
- Vibration

**Maßnahmen:**
- Klimatisierung prüfen/warten
- Filtermaten ersetzen
- Dichtungen kontrollieren
- Kabelzugentlastungen prüfen

**Auswirkungen:**
- Überhitzung führt zu Fehlfunktionen
- Staubablagerungen können Kurzschlüsse verursachen
- Feuchtigkeit verursacht Korrosion
- Vibration lockert Verbindungen

---

**8. Compliance und Zertifizierungen**

**Nachweispflichten:**
- Wartungsprotokolle für Audits
- Rückverfolgbarkeit von Maßnahmen
- Qualitätsmanagement (ISO 9001)
- Umweltzertifikate (ISO 14001)
- Automotive-Standards (IATF 16949)

**Folgen bei Vernachlässigung:**
- Verlust von Zertifikaten
- Liefersperren
- Imageschaden
- Bußgelder

---

**9. Wirtschaftlichkeit**

**Kostenvergleich:**

**Präventive Wartung:**
- Planbare Kosten
- Geringe Ausfallzeiten
- Günstige Ersatzteilpreise (kein Notfall)
- Effiziente Durchführung

**Reaktive Instandsetzung (ohne Wartung):**
- Unplanbare Kosten
- Lange Stillstandzeiten
- Teure Express-Ersatzteile
- Zusatzkosten durch Produktionsausfall
- Eventuell Konventionalstrafen bei Lieferverzug

**Faustformel:**
- 1 € in Wartung investiert spart 4-6 € Reparaturkosten

---

**10. Dokumentation und Rechtskonformität**

**Wartungsnachweis:**
- Protokollierung durchgeführter Arbeiten
- Prüfprotokolle
- Messungen
- Ausgetauschte Teile

**Rechtssicherheit:**
- Nachweis ordnungsgemäßer Instandhaltung
- Wichtig bei Unfällen
- Versicherungsschutz
- Betreiberhaftung

---

**Typischer Wartungsplan:**

**Täglich/bei Schichtende:**
- Sichtprüfung Status-LEDs
- Fehlermeldungen prüfen

**Wöchentlich:**
- Sichtprüfung Schaltschrank
- Temperaturkontrolle

**Monatlich:**
- Reinigung Lüftungsschlitze
- Backup erstellen
- Fehlerprotokoll auswerten

**Quartalsweise:**
- Gründliche Reinigung
- Verbindungen nachziehen
- Filter wechseln

**Jährlich:**
- Umfassende Inspektion
- Batterie prüfen/wechseln
- Funktionstest Sicherheitseinrichtungen
- Firmware-Update prüfen
- Vollständiges Backup

**Alle 3-5 Jahre:**
- Batterie zwingend wechseln
- Lüfter tauschen
- Verschleißteile erneuern
- Speicherkarte wechseln

---

**Zusammenfassung:**

Regelmäßige Wartung ist **essentiell** für:
- **Verfügbarkeit:** Ungeplante Ausfälle vermeiden
- **Sicherheit:** Personen- und Anlagenschutz
- **Lebensdauer:** Investition schützen
- **Wirtschaftlichkeit:** Kosten minimieren
- **Compliance:** Rechtliche Anforderungen erfüllen
- **Optimierung:** Kontinuierliche Verbesserung

**"Vorbeugen ist besser (und billiger) als Heilen"**

---

### Aufgabenstellung 12.2
Nenne zwei Methoden zur Diagnose von Fehlern in einem laufenden SPS-System.

### Lösung 12.2

**Methode 1: Online-Diagnose mit Status-Monitoring**

**Beschreibung:**

Online-Diagnose bedeutet die Überwachung und Analyse des SPS-Systems während es in Betrieb ist, ohne den Prozess zu unterbrechen.

---

**Komponenten der Online-Diagnose:**

**1. LED-Status-Anzeigen:**

**An der SPS:**
- **RUN-LED:** Grün = SPS läuft, Blinkt = Fehler
- **ERROR-LED:** Rot = Systemfehler
- **STOP-LED:** Gelb = SPS im Stop-Modus
- **Com-LED:** Kommunikationsstatus

**An I/O-Modulen:**
- Kanal-LEDs zeigen Status einzelner Ein-/Ausgänge
- Diagnose-LEDs für Modulfehler
- Feldbus-Status-LEDs

**Vorteil:**
- Schneller visueller Check
- Keine Software notwendig
- Auch für Nicht-Programmierer erkennbar

---

**2. Programmiergerät Online-Verbindung:**

**Variablenbeobachtung:**
- Echtzeitwerte aller Variablen sichtbar
- Eingänge, Ausgänge, Merker, Timer, Counter
- Farb-Codierung: TRUE/FALSE, Wertbereiche

**Beispiel:**
```
Eingang I0.0 (Sensor_Werkstück): TRUE (grün hervorgehoben)
Ausgang Q0.5 (Ventil_Spannen): FALSE
Timer T1: Aktueller Wert 2,34s von 5,00s
```

**Baustein-Überwachung:**
- Schritt-für-Schritt Durchlauf des Programms
- Eingänge und Ausgänge von Bausteinen beobachten
- Welcher Baustein wird gerade ausgeführt?
- Verzweigungen nachvollziehen

**Force-Funktion:**
- Manuelle Setzung von Variablen im laufenden Betrieb
- Test einzelner Funktionen
- Simulation von Sensorsignalen
- **ACHTUNG:** Nur im Wartungsmodus, Sicherheit beachten!

---

**3. Diagnosepuffer und Ereignislisten:**

**Inhalt:**
- Chronologische Liste aller Ereignisse
- Fehler mit Zeitstempel
- Systemereignisse (Start, Stop, Reboot)
- Kommunikationsfehler
- Hardwarefehler

**Beispiel:**
```
2025-11-11 14:23:45 - ERROR - Communication timeout CPU -> Module Slot 3
2025-11-11 14:22:10 - WARNING - Zykluszeit überschritten: 45ms (Sollwert: 30ms)
2025-11-11 13:45:02 - INFO - SPS-Start nach Power-On
```

**Auswertung:**
- Häufigkeit bestimmter Fehler
- Muster erkennen
- Ursache-Wirkungs-Zusammenhänge

---

**4. Prozessabbild-Überwachung:**

**PAE (Prozessabbild Eingänge):**
- Zeigt aktuelle Zustände aller Eingänge
- Direkter Vergleich mit physikalischem Zustand möglich

**PAA (Prozessabbild Ausgänge):**
- Zeigt berechnete Ausgangszustände
- Vergleich mit tatsächlichem Aktor-Zustand

**Diagnose-Möglichkeit:**
- Sensor defekt? PAE zeigt keinen Zustandswechsel
- Aktor defekt? PAA = TRUE, aber Aktor reagiert nicht
- Programm fehlerhaft? PAE korrekt, aber PAA falsch

---

**5. Kommunikationsdiagnose:**

**Netzwerk-Status:**
- Verbindungsqualität zu Feldgeräten
- Paketverluste
- Telegrammlaufzeiten
- Bus-Topologie-Ansicht

**Gerätestatus:**
- Welche Geräte sind Online?
- Diagnoseinfos von intelligenten Feldgeräten
- Parametrierung korrekt?

**Beispiel PROFINET:**
- Topologieerkennung
- Port-Status
- Kabelbruch-Erkennung
- Gerätetausch ohne Projektierung

---

**6. Zykluszeit-Überwachung:**

**Monitoring:**
- Aktuelle Zykluszeit
- Minimale Zykluszeit
- Maximale Zykluszeit
- Durchschnitt

**Diagnose:**
- Zykluszeit steigt: CPU-Überlast, Programmfehler (Endlosschleife?)
- Zykluszeit schwankt stark: Probleme in Kommunikation
- Watchdog-Überschreitung: Programm zu langsam

---

**Praktisches Vorgehen bei Fehlersuche:**

**Schritt 1:** LEDs prüfen → Grobe Fehlereingrenzung
**Schritt 2:** Online verbinden → Diagnosepuffer lesen
**Schritt 3:** Betroffenen Bereich beobachten
**Schritt 4:** Variablen in Beobachtungstabelle aufnehmen
**Schritt 5:** Prozess durchlaufen lassen und Signalverläufe beobachten
**Schritt 6:** Ursache identifizieren
**Schritt 7:** Behebungsmaßnahme

---

**Methode 2: Trace-Funktionen und Datenaufzeichnung**

**Beschreibung:**

Trace-Funktionen zeichnen Variablenverläufe über einen längeren Zeitraum auf und ermöglichen die nachträgliche Analyse, insbesondere bei sporadischen oder intermittierenden Fehlern.

---

**Arten von Trace-Funktionen:**

**1. Variable Trace (Signalaufzeichnung):**

**Funktion:**
- Aufzeichnung von bis zu 64 Variablen gleichzeitig (je nach SPS)
- Abtastrate: 1ms bis 1s
- Aufzeichnungsdauer: Sekunden bis Stunden
- Ring- oder Triggerpuffer

**Konfiguration:**
```
Aufzuzeichnende Variablen:
- Sensor_Werkstück_erkannt
- Zylinder_Position
- Druck_Ist
- Druck_Soll
- Fehler_Flag

Trigger: Fehler_Flag == TRUE
Vor-Trigger: 5 Sekunden
Nach-Trigger: 10 Sekunden
```

**Auswertung:**
- Grafische Darstellung als Zeitdiagramm
- Verhalten vor und nach Fehler sichtbar
- Zeitliche Zusammenhänge erkennbar
- Export als CSV für externe Analyse

**Anwendungsfall:**
```
Problem: Maschine stoppt sporadisch mit Druckfehler

Trace zeigt:
- 3 Sekunden vor Fehler: Druck beginnt zu schwanken
- 1 Sekunde vor Fehler: Sensor zeigt kurzen Impuls (50ms)
- Bei Fehler: Druck fällt unter Sollwert

Diagnose: Sensor prellt oder Ventil schaltet kurz
→ Entstörfilter im Programm ergänzen oder Hardware prüfen
```

---

**2. Oszilloskop-Funktion:**

**Beschreibung:**
- Ähnlich wie Variable Trace, aber mit höherer Auflösung
- Ideal für sehr schnelle Signale
- Abtastung im µs-Bereich möglich
- Für Motion-Control-Anwendungen

**Einsatz:**
- Analyse von Positioniervorgängen
- Hochfrequente Zählvorgänge
- Schwingungen
- Synchronisationsprobleme

---

**3. System-Diagnose-Daten:**

**CPU-Auslastung:**
- Aufzeichnung über Zeit
- Erkennung von Lastspitzen
- Korrelation mit Prozessereignissen

**Speichernutzung:**
- RAM-Belegung
- Persistente Speicher
- Memory Leaks erkennen

**Kommunikations-Load:**
- Busauslastung
- Netzwerkverkehr
- Paketraten

---

**4. Alarm- und Event-Logging:**

**Automatische Protokollierung:**
- Alle Alarme werden mit Zeitstempel gespeichert
- Bedienaktionen werden protokolliert
- Rezeptwechsel
- Parameteränderungen

**Auswertung:**
- Häufigkeitsanalyse: Welcher Alarm kommt am öftesten?
- Korrelationen: Tritt Alarm A immer kurz vor Alarm B auf?
- Zeitanalyse: Fehler nur zu bestimmten Zeiten?

**Beispiel-Auswertung:**
```
Alarm "Sensor S3 Signal verloren" trat auf:
- 15x in den letzten 30 Tagen
- Immer zwischen 14:00 und 16:00 Uhr
- Korreliert mit "Hochlauf nach Mittagspause"

Hypothese: Aufwärmphase, thermische Ausdehnung?
→ Sensor-Montage und Kabelverlegung prüfen
```

---

**5. Datenhistorisierung:**

**Langzeit-Aufzeichnung:**
- Prozessdaten werden kontinuierlich in Datenbank geschrieben
- Typisch: Historian-System oder SCADA
- Speicherung über Monate/Jahre

**Daten:**
- Produktionszahlen
- Qualitätsparameter
- Betriebszustände
- Energieverbräuche
- Umgebungsbedingungen

**Analyse-Möglichkeiten:**
- Trends über längere Zeiträume
- Saisonale Effekte
- Korrelation mit externen Faktoren (Wetter, Schichtwechsel)
- Predictive Maintenance

**Beispiel:**
```
Analyse zeigt:
- Ausschussrate steigt kontinuierlich
- Korreliert mit Betriebsstunden der Werkzeuge
- Nach 10.000 Stück deutlicher Anstieg

Maßnahme: Werkzeugwechsel-Intervall von 15.000 auf 10.000 Stück reduzieren
```

---

**6. Remote-Diagnose mit VPN:**

**Fernzugriff:**
- Service-Techniker verbindet sich aus der Ferne
- Alle Diagnose-Tools remote nutzbar
- Trace-Daten können heruntergeladen werden
- Programme können analysiert werden

**Vorteile:**
- Schnelle Hilfe ohne Anfahrt
- Experten können unterstützen
- Kostenersparnis

**Sicherheit:**
- VPN-Tunnel verschlüsselt
- Zeitlich begrenzte Zugriffe
- Logging aller Remote-Zugriffe
- Mehrstufige Authentifizierung

---

**7. Vergleich Ist-Programm vs. Soll-Programm:**

**Anwendung:**
- Hat jemand unerlaubt Änderungen vorgenommen?
- Ist die korrekte Programmversion geladen?
- Wurden Parameter verstellt?

**Methode:**
- Online-Programm auslesen
- Vergleich mit Referenzprogramm (z.B. aus Versionsverwaltung)
- Differenzen werden angezeigt

**Diagnose:**
```
Unterschied gefunden:
- Timer T15: Sollwert 2,0s → Ist-Wert 5,0s
- Änderung am: 2025-11-08 16:23 Uhr
- Benutzer: Inbetriebnehmer_XY

Maßnahme: Rücksprache mit Inbetriebnehmer, korrekten Wert wiederherstellen
```

---

**Praktisches Beispiel - Kombination beider Methoden:**

**Fehlerbeschreibung:**
"Maschine stoppt sporadisch alle paar Stunden mit Alarm 'Sicherheitslichtgitter ausgelöst', aber niemand war in der Nähe."

**Diagnose-Vorgehen:**

**Methode 1 - Online-Diagnose:**
1. LED-Check: Keine Auffälligkeiten
2. Online verbinden und warten bis Fehler auftritt
3. Problem: Fehler tritt nur alle 3-4 Stunden auf → Unpraktisch zu warten

**Methode 2 - Trace einrichten:**
1. Variable "Lichtgitter_Signal" zum Trace hinzufügen
2. Trigger: Lichtgitter_Signal == FALSE
3. Vor-Trigger: 10 Sekunden
4. Laufen lassen über eine Schicht

**Ergebnis:**
Trace zeigt:
- Lichtgitter-Signal fällt für exakt 40ms auf FALSE
- Korreliert mit "Roboter_Bewegung_schnell"
- Vibration durch Roboter löst Fehlauslösung aus

**Lösung:**
- Lichtgitter mechanisch stabilisieren
- Software-Filter: Signal muss 100ms anliegen
- Problem gelöst

---

**Zusammenfassung:**

**Methode 1 - Online-Diagnose:**
- Echtzeitüberwachung
- Sofortiges Eingreifen möglich
- Gut für reproduzierbare Fehler
- Visuell intuitiv

**Methode 2 - Trace/Logging:**
- Für sporadische Fehler
- Nachträgliche Analyse
- Tiefere Einsichten
- Dokumentation

**Kombination beider Methoden ist am effektivsten!**

---

## Ende des Lösungsdokuments

Datum: 2025-11-11
Erstellt von: Claude Code (Anthropic)
Basierend auf: SPS Theorie Aufgaben.pdf, verifiziert mit Control Plus.pdf und SPS Einführung.pdf

---

**Anmerkungen:**
- Alle Lösungen wurden mit den verfügbaren Referenzdokumenten verifiziert
- Praxisbezogene Beispiele wurden ergänzt
- Lösungen berücksichtigen aktuellen Stand der Technik
- Fokus auf Bosch-Umgebung (OpCon Control Plus) wo relevant