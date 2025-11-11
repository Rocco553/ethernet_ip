# Sprechernotizen - EtherNet/IP Präsentation
Benjamin Herrmann | HRL-TVT 4.5 | 10.11.2025

---

## Folie 1: Titelfolie

### Sprechernotizen:
- **Begrüßung:** "Guten Tag, mein Name ist Benjamin Herrmann aus der Abteilung HRL-TVT 4.5"
- **Thema einleiten:** "Heute präsentiere ich Ihnen EtherNet/IP - ein industrielles Kommunikationsprotokoll, das für die Industrie 4.0 eine zentrale Rolle spielt"
- **Zeitrahmen:** Kurz erwähnen, wie lange die Präsentation dauern wird

### Fachbegriffe:
- **EtherNet/IP:** Nicht verwechseln mit "Ethernet over IP" - das Schrägstrich ist wichtig. Steht für "Ethernet Industrial Protocol"
- **Industrie 4.0:** Die vierte industrielle Revolution - Vernetzung von Maschinen, Digitalisierung, IoT

---

## Folie 2: Netflix-Vergleich

### Sprechernotizen:
- **Einstieg:** "Um zu verstehen, was EtherNet/IP macht, habe ich einen Vergleich mit Netflix vorbereitet"
- **Parallelen erklären:** Beide nutzen dasselbe technische Fundament (TCP/IP und Ethernet), aber für unterschiedliche Zwecke
- **Pointe:** "Der große Vorteil: Wir brauchen keine teure Spezial-Hardware wie bei älteren Feldbussystemen"

### Fachbegriffe zu erklären:
- **TCP/IP:** Transmission Control Protocol / Internet Protocol - Die Grundlage des Internets. TCP sorgt für zuverlässige Verbindungen, IP für die Adressierung
- **Ethernet:** Der Kabel-Standard für Netzwerke (Layer 1 + 2 im OSI-Modell)
- **Echtzeit-Daten:** Daten, die ohne merkliche Verzögerung übertragen werden müssen (1-100 Millisekunden)
- **Produktionsdaten:** Sensormesswerte, Steuerungsbefehle, Maschinenzustände

### Tipps:
- Betone den Netflix-Vergleich - er macht das Thema greifbarer
- Standard-Hardware = Kostenersparnis hervorheben

---

## Folie 3: Funktionsprinzip

### Sprechernotizen:
- **OSI-Modell ansprechen:** "EtherNet/IP nutzt die unteren vier Layer von Standard-Ethernet und TCP/IP"
- **CIP betonen:** "Das Besondere ist CIP auf den oberen drei Layern - das ist die industrielle 'Intelligenz'"
- **Zwei Wege erklären:** "Je nachdem, was wir übertragen wollen, nutzen wir unterschiedliche Kommunikationswege"

### Fachbegriffe zu erklären:
- **OSI-Modell:** Open Systems Interconnection - Ein 7-Schichten-Modell, das beschreibt, wie Netzwerkkommunikation funktioniert
  - Layer 1 (Bitübertragung): Physikalische Kabel
  - Layer 2 (Sicherung): MAC-Adressen, Ethernet-Frames
  - Layer 3 (Vermittlung): IP-Adressen, Routing
  - Layer 4 (Transport): TCP/UDP - Wie Daten transportiert werden
  - Layer 5-7 (Anwendung): CIP - Die industrielle Logik

- **CIP (Common Industrial Protocol):** Der industrielle Standard, der definiert, wie Geräte miteinander sprechen. Wird auch von anderen Protokollen wie DeviceNet verwendet

- **Implicit Messages (I/O):**
  - "Implicit" = implizit, vorab vereinbart
  - Nutzt UDP (User Datagram Protocol)
  - Schnell, weil keine Bestätigung erforderlich
  - Zyklisch = regelmäßig, z.B. alle 10ms
  - Für zeitkritische Sensordaten und Aktorsteuerung

- **Explicit Messages (Config):**
  - "Explicit" = explizit angefragt
  - Nutzt TCP (zuverlässig)
  - Bei Bedarf = nicht regelmäßig, nur wenn nötig
  - Für Konfiguration, Diagnose, File-Transfer

### Tipps:
- OSI-Modell nicht zu tief erklären - nur die Grundidee
- Die zwei Kommunikationswege mit Beispielen verdeutlichen: "Sensordaten = UDP/schnell, Konfiguration = TCP/zuverlässig"

---

## Folie 4: Kommunikationsmodelle

### Sprechernotizen:
- **Producer-Consumer erklären:** "Stellen Sie sich einen Temperatursensor vor, der seine Messwerte an mehrere Empfänger sendet"
- **Client-Server erklären:** "Wie wenn Sie eine Webseite aufrufen - Sie fragen, der Server antwortet"
- **Unterschied betonen:** "Producer-Consumer ist effizienter für Echtzeitdaten, weil ein Sender mehrere Empfänger erreicht"

### Fachbegriffe zu erklären:
- **Producer-Consumer (Multicast):**
  - Producer = Erzeuger (z.B. Temperatursensor)
  - Consumer = Verbraucher (z.B. SPS, HMI, Logger, Alarmanlage)
  - Multicast = Eine Nachricht an viele Empfänger gleichzeitig
  - Vorteil: Netzwerk wird nicht mehrfach belastet
  - 10-100ms Zykluszeit typisch

- **Client-Server (Point-to-Point):**
  - Client = Anfragender (z.B. Laptop, HMI)
  - Server = Antwortender (z.B. SPS)
  - Request-Response = Frage → Antwort
  - TCP für Zuverlässigkeit
  - Beispiel: "Gib mir die IP-Adresse des Sensors"

- **I/O:** Input/Output = Eingänge/Ausgänge (Sensoren/Aktoren)
- **SPS:** Speicherprogrammierbare Steuerung (engl. PLC - Programmable Logic Controller)
- **HMI:** Human Machine Interface - Bedienterminal
- **Alarmanlage:** System zur Überwachung von Grenzwerten

### Tipps:
- Das Bild zeigt deutlich den Unterschied - darauf verweisen
- Betone: "EtherNet/IP nutzt beide Modelle je nach Anwendung"

---

## Folie 5: Performance

### Sprechernotizen:
- **Geschwindigkeit einordnen:** "1-100ms Zykluszeit - das klingt vielleicht langsam, aber für 90% aller Industrie-Anwendungen ist das mehr als ausreichend"
- **Vergleich nutzen:** "Unsere menschliche Reaktionszeit liegt bei etwa 100ms - EtherNet/IP ist also schneller als wir wahrnehmen können"
- **Praxisbeispiel:** "Bei Bosch Reutlingen aktualisieren wir Sensordaten alle 100ms - das ist schnell genug für Qualitätskontrolle und Schraubvorgänge"

### Fachbegriffe zu erklären:
- **Zykluszeit:** Die Zeit zwischen zwei Datenupdates. 1-100ms bedeutet: 10-1000 Updates pro Sekunde
- **Mbit/s:** Megabit pro Sekunde - Übertragungsgeschwindigkeit
  - 10 Mbit/s = ältere Geräte
  - 100 Mbit/s = Standard heute
  - 1000 Mbit/s (1 Gbit/s) = Moderne Industrial Switches

- **Schweißroboter (ca. 200 km/h):** Extrem schnelle Bewegungen, die präzise gesteuert werden müssen. Bei 200 km/h bewegt sich der Roboter etwa 5,5 cm in 1ms - das zeigt, warum schnelle Kommunikation wichtig ist

- **Hochgeschwindigkeits-Förderband (bis 2 m/s):** 2 Meter pro Sekunde = 7,2 km/h. Bei 100ms Zykluszeit bewegt sich das Band 20cm - ausreichend für Positions-Tracking

### Tipps:
- Betone den Unterschied zwischen "schnell genug" und "ultra-schnell"
- Die Vergleiche (Gaming-Ping, menschliches Auge) machen es greifbar
- Klarstellen: "Für Robotik an der Leistungsgrenze gibt es EtherCAT, aber das brauchen die wenigsten"

---

## Folie 6: Topologie

### Sprechernotizen:
- **Stern-Topologie erklären:** "Die Standard-Netzwerkstruktur - alle Geräte hängen an einem zentralen Switch"
- **Vorteile betonen:** "Wenn ein Sensor ausfällt, läuft der Rest weiter. Bei einer Linie würde alles dahinter ausfallen"
- **Verkabelung:** "Standard Ethernet-Kabel wie im Büro, nur robuster für die Fabrikhalle"

### Fachbegriffe zu erklären:
- **Stern-Topologie:** Alle Geräte sind sternförmig mit einem zentralen Switch verbunden
  - Vorteil: Ausfall eines Geräts betrifft nicht die anderen
  - Nachteil: Switch ist Single Point of Failure (kann durch Redundanz gelöst werden)

- **SPS:** Speicherprogrammierbare Steuerung - das "Gehirn" der Anlage
- **Panel:** HMI / Bedienterminal mit Touchscreen
- **I/O-Module:** Input/Output Module - sammeln Sensordaten und steuern Aktoren
- **Switch:** Netzwerk-Verteiler, der Datenpakete intelligent weiterleitet

- **Verkabelung:**
  - **CAT5e/CAT6:** Category 5 enhanced / Category 6 - Kabelstandards
    - CAT5e: bis 1 Gbit/s
    - CAT6: bis 10 Gbit/s
  - **100m Reichweite:** Maximale Kabellänge ohne Signalverstärker
  - **RJ45-Stecker:** Der Standard-Ethernet-Stecker (8 Pins)
  - **Günstig & überall verfügbar:** Im Gegensatz zu proprietären Feldbus-Kabeln

- **Alternative Topologien:**
  - **Baum-Topologie:** Hierarchisch verschachtelte Switches für große Anlagen
  - **Ring-Topologie:** Kabel bilden einen geschlossenen Kreis - höhere Ausfallsicherheit (wenn ein Kabel bricht, läuft es über die andere Richtung weiter)

### Tipps:
- Das Schaubild zeigt die Hierarchie deutlich - darauf verweisen
- Betone die Flexibilität: "Einfach zu erweitern - neues Gerät? Einfach ins nächste freie Switch-Port einstecken"

---

## Folie 7: Protokolleigenschaften - CIP

### Sprechernotizen:
- **CIP als Kern erklären:** "CIP ist das Herzstück - es definiert, wie industrielle Geräte miteinander sprechen"
- **Objektorientiert:** "Jedes Gerät wird als Objekt mit Eigenschaften dargestellt - ähnlich wie in der Programmierung"
- **Herstellerunabhängig:** "Von der ODVA verwaltet - einer Non-Profit-Organisation. Kein Hersteller-Lock-in!"

### Fachbegriffe zu erklären:
- **CIP (Common Industrial Protocol):** Der gemeinsame industrielle Standard

- **Objektorientiert:**
  - Jedes Gerät = Objekt mit:
    - **Attributes (Attributen):** Eigenschaften wie Temperatur, Status, Seriennummer
    - **Services (Diensten):** Funktionen wie "Lesen", "Schreiben", "Reset"
    - **Connections (Verbindungen):** Kommunikationswege zu anderen Geräten
    - **Behaviors (Verhalten):** Was passiert bei bestimmten Events

- **ODVA (Open DeviceNet Vendor Association):**
  - Non-Profit-Organisation
  - Verwaltet CIP, DeviceNet, EtherNet/IP
  - Über 300 Mitgliedsfirmen
  - Offener Standard - jeder kann Geräte entwickeln

- **CIP auch verwendet bei:**
  - **DeviceNet:** Über CAN-Bus (Controller Area Network)
  - **ControlNet:** Älteres deterministisches Netzwerk
  - **CompoNet:** Kompaktes Sensornetzwerk für kleine Geräte

- **TCP für komplexe Nachrichten:**
  - **Konfiguration:** Parameter ändern, Geräte einrichten
  - **Diagnose:** Status abfragen, Fehlermeldungen lesen
  - **File-Transfer:** Firmware-Updates, Rezepte laden
  - **Garantierte Zustellung:** TCP bestätigt jedes Paket

- **UDP für zeitkritische I/O:**
  - **Sensordaten:** Temperatur, Druck, Position
  - **Aktoren-Steuerung:** Motor ein/aus, Ventil öffnen/schließen
  - **Minimale Latenz:** Keine Wartezeit auf Bestätigung
  - **Multicast möglich:** Ein Sensor, viele Empfänger

- **Praktische Features:**
  - **DHCP:** Dynamic Host Configuration Protocol - automatische IP-Vergabe wie im Heimnetzwerk
  - **BootP:** Bootstrap Protocol - Alternative zu DHCP
  - **Webserver:** Jedes Gerät hat eine eingebaute Webseite zur Diagnose - einfach IP im Browser eingeben!
  - **Standard-IT-Tools:** Wireshark (Paket-Analyse), Ping (Erreichbarkeit), Traceroute (Netzwerkpfad)

### Tipps:
- Der objektorientierte Ansatz ist modern - das kann man als Vorteil verkaufen
- Betone den Webserver: "Keine Spezialsoftware nötig - einfach Browser öffnen!"
- ODVA zeigt: "Das ist kein proprietärer Standard eines einzelnen Herstellers"

---

## Folie 8: Kosten

### Sprechernotizen:
- **Hauptvorteil:** "0€ Lizenzgebühren - das ist ein riesiger Unterschied zu manchen anderen Systemen"
- **Standard-Hardware:** "Die Komponenten sind günstig, weil sie in Massen für normale Netzwerke produziert werden"
- **Kostentabelle durchgehen:** Die Zahlen sind realistisch - evtl. kurz auf die Spanne hinweisen

### Fachbegriffe zu erklären:
- **Lizenzgebühren:** Bei manchen Systemen (z.B. EtherCAT) fallen Lizenzkosten pro Gerät an
- **Standard-Komponenten:** Handelsübliche Ethernet-Hardware ohne spezielle Modifikationen

- **Kostenaufschlüsselung:**
  - **Standard-Switch (5 Ports):** 50-200€
    - Für Büro-Anwendungen
    - Meist ausreichend für unkritische Bereiche

  - **Industrial-Switch (16 Ports):** 500-2000€
    - Robustes Gehäuse (IP65/67)
    - Erweiterte Temperaturbereich (-40°C bis +75°C)
    - Redundanz-Funktionen
    - DIN-Rail-Montage für Schaltschrank

  - **Ethernet-Kabel CAT6:** 1-5€/Meter
    - Industrieausführung etwas teurer
    - Geschirmt für EMV-Schutz (elektromagnetische Verträglichkeit)

  - **EtherNet/IP Adapter:** 300-800€
    - Verbindet "dumme" Geräte mit dem Netzwerk
    - Beispiel: Legacy-Sensor ohne Ethernet → Adapter → Netzwerk

  - **Lizenzgebühren:** 0€ - Offener Standard!

### Einsparungen gegenüber anderen Systemen:
- **Kein Vendor Lock-in:** Komponenten von verschiedenen Herstellern kombinierbar
- **Standard-IT-Komponenten:** Kann zur Not auch einen Büro-Switch verwenden
- **Einfachere Schulung:** IT-Wissen aus anderen Bereichen übertragbar
- **Geringere Lagerhaltung:** Standard-Teile sind überall verfügbar
- **Längere Verfügbarkeit:** Standard-Komponenten werden länger produziert

### Tipps:
- Die 0€ Lizenz ist ein starkes Verkaufsargument
- Kostenbeispiel konkret machen: "Ein kleines Netzwerk mit 10 Geräten kostet etwa 2000-3000€ für die Infrastruktur"

---

## Folie 9: Diagnose und Fehlersuche

### Sprechernotizen:
- **Einfachheit betonen:** "Drei Schritte reichen oft aus, um 90% der Probleme zu finden"
- **LED-Check:** "Erste Anlaufstelle - schnell und ohne Tools"
- **Praxisbeispiel durchgehen:** Das zeigt, wie schnell Probleme gelöst werden können

### Fachbegriffe zu erklären:
- **Integrierte Diagnose-Tools:**

  - **Webserver:**
    - Jedes EtherNet/IP-Gerät hat einen eingebauten Webserver
    - Einfach IP-Adresse im Browser eingeben: z.B. `192.168.1.100`
    - Zeigt: Status, Fehlermeldungen, Konfiguration, Statistiken
    - Kein Spezial-Tool nötig!

  - **LED-Status:**
    - **Grün:** Alles OK, Gerät läuft normal
    - **Rot:** Fehler (z.B. Konfigurationsfehler, Hardware-Problem)
    - **Blinken:** Kommunikation aktiv (je schneller, desto mehr Traffic)
    - Meist zwei LEDs: Network + Module Status

  - **Standard-IT-Tools:**
    - **Wireshark:** Paket-Sniffer - zeigt alle Netzwerk-Pakete
      - Kostenlos, Open Source
      - Kann EtherNet/IP-Protokoll dekodieren
      - Für tiefe Fehleranalyse

    - **Ping:** Erreichbarkeitstest
      - `ping 192.168.1.100`
      - Zeigt, ob Gerät im Netzwerk antwortet
      - Zeigt auch Reaktionszeit (wichtig für Diagnose)

    - **LLDP (Link Layer Discovery Protocol):**
      - Automatische Topologie-Erkennung
      - Geräte melden sich mit Name, Port, Capabilities
      - Tool zeigt Netzwerk-Karte automatisch

### Fehlersuche in 3 Schritten:
1. **LED-Check:** Visuell prüfen - dauert 30 Sekunden
2. **Ping-Test:** Netzwerk-Erreichbarkeit - dauert 10 Sekunden
3. **Webserver:** Detaillierte Diagnose - dauert 2 Minuten

### Beispiel Fehlerdiagnose - Erklärung:
- **Problem:** Sensor meldet sich nicht mehr
- **LED grün:** Sensor selbst funktioniert
- **Switch blinkt:** Daten werden gesendet
- **Ping timeout:** Sensor antwortet nicht auf Netzwerk-Anfragen
- **→ Ursache:** IP-Adresse doppelt vergeben
  - Zwei Geräte haben dieselbe IP
  - Netzwerk weiß nicht, an wen es senden soll
- **→ Fix:** DHCP neu konfigurieren oder manuelle IP vergeben
- **Problem in wenigen Minuten gelöst**

### Tipps:
- Die drei Schritte sind ein praktisches Schema - gut zu merken
- Betone den Webserver als "Killer-Feature" - keine Spezialsoftware nötig
- Das Beispiel zeigt: Fehlersuche ist systematisch und schnell

---

## Folie 10: Sicherheit / Cybersecurity

### Sprechernotizen:
- **Relevanz:** "2023 gab es 70% mehr Cyberangriffe auf Industrieanlagen - das Thema ist hochaktuell"
- **Defense-in-Depth:** "Mehrere Sicherheitsschichten - wie Zwiebel-Prinzip"
- **X.509 Zertifikate:** "Wie HTTPS im Browser - jedes Gerät bekommt ein digitales Zertifikat"

### Fachbegriffe zu erklären:
- **Warum wichtig?**
  - 2023: 70% mehr Cyberangriffe auf Industrieanlagen
  - Produktionsstillstand kostet Millionen pro Tag
  - IT + OT wachsen zusammen = größere Angriffsfläche
  - **IT:** Information Technology (Büro-IT)
  - **OT:** Operational Technology (Produktions-IT)

- **Technologie - TLS/DTLS Verschlüsselung:**
  - **TLS (Transport Layer Security):**
    - Verschlüsselt TCP-Verbindungen
    - Wie HTTPS im Browser
    - Für Konfiguration & Diagnose

  - **DTLS (Datagram Transport Layer Security):**
    - Verschlüsselt UDP-Verbindungen
    - Für Echtzeitdaten (I/O)
    - Minimaler Overhead

  - **AES-Verschlüsselung:**
    - Advanced Encryption Standard
    - Militärischer Standard
    - 128/256 Bit Schlüssellänge

- **X.509 Zertifikate:**
  - Digitale Ausweise für Geräte
  - Jedes Gerät bekommt eindeutiges Zertifikat
  - Eindeutige Authentifizierung - kein Gerät kann sich als anderes ausgeben
  - Wie SSL-Zertifikate bei Webseiten

- **Features:**
  - **Ende-zu-Ende-Verschlüsselung:** Daten sind auf gesamtem Weg verschlüsselt
  - **Benutzer-Authentifizierung:** Login mit Benutzername/Passwort oder Zertifikat
  - **Zugriffskontrolle:** Wer darf was? (Read/Write/Admin)
  - **Man-in-the-Middle Erkennung:** Warnung wenn jemand Kommunikation abfängt

- **Defense-in-Depth (3 Sicherheitsschichten):**
  1. **Firewall (Netzwerk):**
     - Trennt Produktionsnetzwerk vom Büronetzwerk
     - Nur erlaubte Verbindungen durchgelassen

  2. **Network Segmentation:**
     - Netzwerk in Zonen aufteilen
     - Roboter-Netzwerk getrennt von Sensor-Netzwerk
     - Bei Angriff wird nur eine Zone kompromittiert

  3. **CIP Security (Gerät):**
     - Letzte Verteidigungslinie
     - Verschlüsselung + Authentifizierung auf Protokollebene
     - Auch innerhalb der Zone geschützt

### Tipps:
- Das Thema ist ernst - Statistik zeigt die Dringlichkeit
- Defense-in-Depth-Konzept ist verständlich: "Mehrere Schlösser an der Tür"
- X.509 mit HTTPS-Vergleich erklären - das kennen alle

---

## Folie 11: Industrie 4.0 Integration

### Sprechernotizen:
- **Durchgängigkeit:** "Von der kleinsten Schraube bis zur Cloud - alles über EtherNet/IP verbunden"
- **4 Ebenen erklären:** "Sensoren → Steuerung → Management → Cloud - klassische Automatisierungspyramide"
- **Transparenz betonen:** "Jederzeit Echtzeit-Einblick in jeden einzelnen Sensor"

### Fachbegriffe zu erklären:
- **Die 4 Ebenen der Automatisierung:**

  1. **Sensoren / Aktoren (Feldebene):**
     - Unterste Ebene - direkt an der Maschine
     - Sensoren: Messen (Temperatur, Druck, Position)
     - Aktoren: Bewegen (Motoren, Ventile, Zylinder)

  2. **Steuerung / SPS (Steuerungsebene):**
     - Programmiert die Maschinenlogik
     - Echtzeit-Verarbeitung
     - Koordiniert Abläufe

  3. **MES / SCADA (Management-Ebene):**
     - **MES:** Manufacturing Execution System
       - Produktionsplanung
       - Auftragsmanagement
       - Qualitätssicherung
     - **SCADA:** Supervisory Control And Data Acquisition
       - Überwachung
       - Bedienung
       - Visualisierung

  4. **Cloud / ERP (Geschäftsebene):**
     - **ERP:** Enterprise Resource Planning (z.B. SAP)
     - Buchhaltung, Warenwirtschaft
     - Business Intelligence
     - Cloud-Analytics

- **Industrie 4.0 Features:**
  - **Echtzeit-Daten für MES/ERP:**
    - Produktionszahlen live verfügbar
    - Keine manuelle Erfassung mehr
    - Automatische Buchung ins ERP

  - **Cloud-Anbindung (OPC UA, MQTT):**
    - **OPC UA:** Open Platform Communications Unified Architecture
      - Standard für industrielle Cloud-Kommunikation
      - EtherNet/IP kann OPC UA-Daten einpacken
    - **MQTT:** Message Queuing Telemetry Transport
      - Leichtgewichtiges Protokoll für IoT
      - Für Cloud-Dienste (AWS, Azure, etc.)

  - **Horizontale Integration (Fabrik-zu-Fabrik):**
    - Standorte vernetzen
    - Beispiel: Werk A meldet an Werk B: "Wir brauchen mehr Teile"

  - **Vertikale Integration (Sensor-zu-ERP):**
    - Durchgängiger Datenfluss
    - Sensor → SPS → MES → ERP → Cloud
    - Keine Medienbrüche

  - **Remote-Wartung möglich:**
    - Service-Techniker kann von außen zugreifen
    - Ferndiagnose
    - Software-Updates über Internet

  - **Predictive Maintenance:**
    - Vorausschauende Wartung
    - Maschinendaten analysieren
    - Verschleiß vorhersagen bevor Ausfall

- **Die 4 Prinzipien von Industrie 4.0:**
  1. **Vernetzung:** EtherNet/IP verbindet alles
  2. **Transparenz:** Echtzeit-Daten von jedem Sensor
  3. **Technische Assistenz:** Systeme unterstützen Entscheidungen (z.B. Wartungs-Empfehlungen)
  4. **Dezentrale Entscheidungen:** Geräte reagieren selbstständig (z.B. Not-Stopp ohne zentrale Steuerung)

### Tipps:
- Das Schaubild mit den 4 Ebenen ist sehr klar - darauf verweisen
- Betone: "EtherNet/IP ermöglicht den durchgängigen Datenfluss - das ist der Kern von Industrie 4.0"
- Predictive Maintenance ist ein starkes Beispiel für den Mehrwert

---

## Folie 12: Praxisbeispiel Bosch Reutlingen

### Sprechernotizen:
- **Konkret werden:** "Das ist keine Theorie - das läuft wirklich bei uns im Werk"
- **Zahlen beeindrucken:** "8,6 Millionen Messages pro Schicht - das zeigt die Leistungsfähigkeit"
- **Mehrwert:** "Diese Daten ermöglichen Qualitätssicherung in Echtzeit und vorausschauende Wartung"

### Fachbegriffe zu erklären:
- **Aufbau der Montagelinie:**
  - **24 Roboter-Arbeitsplätze:**
    - Verschiedene Montage-Schritte
    - Koordiniert über EtherNet/IP

  - **180 Sensoren:**
    - **Drucksensoren:** Überwachen Pneumatik (Pressvorgang, Zylinder)
    - **Positionssensoren:** Prüfen, ob Teile korrekt platziert sind
    - **Qualitätssensoren:** Messen, Wiegen, Kamera-Inspektion

  - **12 Schweißroboter:**
    - Komplexe Bewegungsabläufe
    - Echtzeitkoordination
    - Qualitätsüberwachung (Schweißstrom, -spannung)

  - **3 Steuerungen (SPS):**
    - Mehrere SPS koordinieren Teilbereiche
    - Kommunizieren untereinander über EtherNet/IP
    - Redundanz für höhere Verfügbarkeit

- **Datenfluss in Echtzeit:**
  - **Produktionszahlen → MES:**
    - Wie viele Teile produziert?
    - Welche Chargen-Nummer?
    - Takt-Zeiten

  - **Qualitätsdaten → SAP:**
    - Messwerte dokumentiert
    - Rückverfolgbarkeit (Traceability)
    - Automatische Qualitätsfreigabe

  - **Maschinendaten → Wartungs-Dashboard:**
    - Verschleiß-Indikatoren
    - Betriebsstunden
    - Fehlerhistorie
    - Predictive Maintenance

  - **Energieverbrauch → Energie-Management:**
    - Stromverbrauch pro Bauteil
    - Lastspitzen erkennen
    - CO2-Bilanz

- **Zahlen pro Schicht (8 Stunden):**
  - **2.400 Bauteile produziert:**
    - = 300 Teile/Stunde
    - = 5 Teile/Minute
    - = 12 Sekunden Taktzeit

  - **432.000 Datenpunkte übertragen:**
    - 180 Sensoren × 2.400 Bauteile = 432.000
    - Jedes Bauteil wird von jedem Sensor erfasst

  - **Zustandsupdate alle 50ms:**
    - = 20 Updates pro Sekunde
    - Echtzeitüberwachung

  - **→ 8,6 Mio. Messages pro Schicht:**
    - 8 Stunden = 28.800 Sekunden
    - 28.800 s × 300 Messages/s = 8,64 Millionen

  - **→ 300 Messages pro Sekunde:**
    - Durchschnittliche Netzwerk-Last
    - Bei 100 Mbit/s Netzwerk nur minimale Auslastung

### Tipps:
- Die konkreten Zahlen machen es greifbar
- Betone den Mehrwert: "Diese Daten werden nicht nur übertragen, sondern aktiv genutzt für Qualität und Effizienz"
- 8,6 Millionen Messages klingt viel - in Relation zum Netzwerk ist es aber locker zu bewältigen

---

## Folie 13: Vergleich mit Konkurrenz

### Sprechernotizen:
- **Objektiv bleiben:** "Es gibt keinen perfekten Feldbus - jeder hat seine Stärken"
- **Tabelle durchgehen:** Die wichtigsten Unterschiede hervorheben
- **EtherNet/IP Stärken:** "Beste IT-Integration und einfachste Handhabung"

### Fachbegriffe zu erklären:
- **PROFINET:**
  - Entwickelt von Siemens
  - Marktführer in Europa (besonders Deutschland)
  - 65+ Millionen installierte Knoten
  - Ähnlich wie EtherNet/IP, aber andere Architektur
  - 0,25-100ms Zykluszeit (Hard-Realtime möglich)
  - Standard-Hardware, kostenlos
  - Mittlere Einstiegshürde
  - Stark in Automotive und Fertigungsindustrie

- **EtherCAT:**
  - Entwickelt von Beckhoff
  - Ultra-schnell (<0,1ms = 100 Mikrosekunden)
  - Hard-Realtime garantiert
  - **Achtung:** Spezielle Hardware nötig (EtherCAT-Slaves)
  - Lizenzgebühren pro Gerät
  - IT-Integration schwieriger (proprietäres Protokoll)
  - Komplexe Einrichtung
  - 10+ Millionen Knoten
  - Perfekt für High-Speed Motion Control

- **Vergleichskriterien Erklärung:**
  - **Verbreitung:**
    - EtherNet/IP: USA, Asien (Rockwell dominiert)
    - PROFINET: Europa (Siemens dominiert)
    - EtherCAT: Weltweit in Nischen (Motion Control)

  - **Zykluszeit:**
    - Soft-Realtime: Meistens pünktlich, aber nicht garantiert
    - Hard-Realtime: Garantiert pünktlich, sonst Fehler

  - **Hardware:**
    - Standard: Normale Ethernet-Komponenten
    - Speziell: Spezielle Chips/ASICs nötig

  - **Lizenzkosten:**
    - EtherNet/IP, PROFINET: Kostenlos
    - EtherCAT: Ca. 1-2€ pro Gerät (ETG-Mitgliedschaft)

  - **IT-Integration:**
    - EtherNet/IP: 5 Sterne (Standard TCP/IP)
    - PROFINET: 4 Sterne (braucht spezielle Treiber)
    - EtherCAT: 3 Sterne (proprietär, komplexer)

  - **Einstiegshürde:**
    - Einfach: Plug & Play, wenig Fachwissen
    - Mittel: Grundkenntnisse nötig
    - Komplex: Spezialwissen erforderlich

  - **Installierte Knoten:**
    - Anzahl der weltweit installierten Geräte
    - Zeigt Marktdurchdringung und Akzeptanz

### Tipps:
- Die Tabelle ist sehr übersichtlich - Punkt für Punkt durchgehen
- Nicht zu sehr auf Konkurrenz einschlagen - objektiv bleiben
- Klarstellen: "Für 90% der Anwendungen reicht EtherNet/IP völlig aus"

---

## Folie 14: Wann welcher Feldbus?

### Sprechernotizen:
- **Entscheidungshilfe geben:** "Je nach Anforderung gibt es die optimale Wahl"
- **EtherNet/IP Sweet Spot:** "Überall wo IT/OT-Integration wichtig ist"
- **Fazit betonen:** "Meistens reicht EtherNet/IP völlig aus"

### Wann EtherNet/IP perfekt ist:
- **IT/OT-Integration wichtig:**
  - Cloud-Anbindung geplant
  - MES/ERP-Integration erforderlich
  - Standard-IT-Know-how im Team
  - Remote-Zugriff von außen

- **Standard-Hardware gewünscht:**
  - Budget-Beschränkungen
  - Keine Vendor-Lock-in
  - Einfache Beschaffung
  - Langfristige Verfügbarkeit

- **USA/Asien-Markt:**
  - Rockwell Automation stark verbreitet
  - Allen-Bradley SPS
  - Standard in vielen US-Werken

- **Montage, Verpackung, Prozess:**
  - Nicht ultra-zeitkritisch
  - Viele Sensoren/Aktoren
  - Flexible Topologie
  - Erweiterbarkeit wichtig

### Wann PROFINET besser ist:
- **Schnellere Zykluszeiten nötig:**
  - <10ms erforderlich
  - Hard-Realtime wichtig
  - Präzise Synchronisation

- **Siemens-Umfeld:**
  - Simatic S7 SPS
  - TIA Portal Engineering
  - Bestehende PROFINET-Infrastruktur

- **Europa-Markt:**
  - Deutsche Automotive-Industrie
  - Maschinenbau

- **Automotive-Industrie:**
  - Hochpräzise Montage
  - Kurze Taktzeiten
  - Große Stückzahlen

### Wann EtherCAT besser ist:
- **Ultra-schnelle Motion Control:**
  - <1ms Zykluszeit
  - Mehrere Achsen synchronisieren
  - CNC-Maschinen

- **High-Speed Robotik (<100µs):**
  - Delta-Roboter (Picking)
  - Hochgeschwindigkeits-Handling
  - Präzisionsmontage

- **Kompakte Maschinen:**
  - Wenige, hochperformante Geräte
  - Platz für spezialisierte Hardware

- **Höchste Performance erforderlich:**
  - Motion Control als Kernkompetenz
  - Keine Kompromisse bei Latenz

### Fazit (wichtig!):
- "Es gibt nicht **den besten** Feldbus - es kommt auf die Anwendung an!"
- "Für die **meisten Standard-Anwendungen** ist EtherNet/IP mehr als ausreichend"
- "EtherNet/IP bietet die **beste IT-Integration** und **einfachste Handhabung**"

### Tipps:
- Diese Folie ist sehr wertvoll für Entscheidungsträger
- Betone, dass es kein "Entweder-Oder" ist - manchmal werden auch mehrere Systeme kombiniert
- Das Fazit ist wichtig: EtherNet/IP ist für die meisten Fälle die beste Wahl

---

## Folie 15: Zusammenfassung

### Sprechernotizen:
- **Kernbotschaften wiederholen:** Die wichtigsten Punkte nochmal betonen
- **Stärken klar herausstellen:** IT-Integration und Kosteneffizienz
- **Schwächen ehrlich nennen:** Nicht für Ultra-High-Speed
- **Schlusssatz:** "Was WLAN für uns ist, ist EtherNet/IP für die Fabrik - Standard, zuverlässig, allgegenwärtig"

### Stärken - Detailliert erklärt:
- **Einfache Integration in IT-Landschaft:**
  - Standard TCP/IP
  - Keine Gateways nötig
  - IT-Personal kann mitarbeiten
  - Cloud-ready

- **Kosteneffizient (Standard-Hardware):**
  - Keine Spezial-Komponenten
  - Günstige Beschaffung
  - Große Auswahl an Anbietern

- **Weit verbreitet (30+ Mio. Knoten):**
  - Bewährte Technologie
  - Große Community
  - Viel Support verfügbar

- **Offener Standard (keine Lizenzkosten):**
  - Keine laufenden Gebühren
  - Kein Vendor-Lock-in
  - Innovation durch Wettbewerb

- **IT-Tools verwendbar:**
  - Wireshark, Ping, Traceroute
  - Standard-Network-Management
  - Keine Spezialsoftware

- **Industrie 4.0 ready:**
  - Cloud-Integration
  - IoT-Kompatibilität
  - Zukunftssicher

- **Gute Absicherung vor Angriffen:**
  - TLS/DTLS Verschlüsselung
  - X.509 Zertifikate
  - Defense-in-Depth

- **Zukunftssicher (IoT, Cloud):**
  - Weiterentwicklung aktiv
  - Neue Standards (TSN, OPC UA)
  - Langfristig unterstützt

### Schwächen - Ehrlich kommunizieren:
- **Nicht für Ultra-High-Speed (Soft-Realtime):**
  - 1-100ms typisch
  - Für 90% ausreichend, aber nicht für extreme Motion Control
  - Deterministik nicht garantiert

- **In Europa weniger verbreitet als PROFINET:**
  - Siemens dominiert Europa
  - Weniger lokaler Support
  - Aber: Wächst stetig

- **Keine harten Echtzeit-Garantien:**
  - Soft-Realtime = meistens pünktlich
  - Hard-Realtime = immer pünktlich
  - Für sicherheitskritische Anwendungen kann das ein Problem sein
  - Lösung: TSN (Time-Sensitive Networking) kommt

### Perfekt für:
- **Montage-Linien:** Wie Bosch Reutlingen
- **Verpackungsanlagen:** Automatische Verpackung, Etikettierung
- **Prozess-Automation:** Chemie, Pharma, Lebensmittel
- **Fabriken mit IT/OT-Integration:** Moderne Smart Factories
- **90% aller Industrie-Anwendungen:** Die meisten Anwendungen brauchen keine Ultra-High-Speed

### Der Schlusssatz (wichtig!):
**"Was WLAN für uns ist, ist EtherNet/IP für die Fabrik"**
- Allgegenwärtig
- Standard
- Zuverlässig
- Einfach zu nutzen
- Jeder kennt es
- Zukunftssicher

### Tipps für den Abschluss:
- Die Zusammenfassung sollte kurz und prägnant sein
- Die wichtigsten 3-5 Punkte hervorheben
- Mit dem WLAN-Vergleich enden - das bleibt hängen
- Offene Fragen einladen: "Gibt es noch Fragen?"
- Danke für Aufmerksamkeit

---

## Allgemeine Präsentationstipps:

### Körpersprache & Auftreten:
- Ruhig und selbstbewusst auftreten
- Blickkontakt halten
- Nicht zu schnell sprechen
- Pausen einlegen nach wichtigen Punkten

### Mit Fachbegriffen umgehen:
- Beim ersten Mal immer die Abkürzung ausschreiben
  - "CIP - Common Industrial Protocol"
  - "SPS - Speicherprogrammierbare Steuerung"
- Dann kann man die Abkürzung verwenden
- Bei komplexen Begriffen: Analogien nutzen (wie der Netflix-Vergleich)

### Zeitmanagement:
- Pro Folie ca. 2-3 Minuten einplanen
- 15 Folien = ca. 30-45 Minuten
- Puffer für Fragen einplanen

### Bei Fragen:
- Wenn du die Antwort nicht weißt: Ehrlich sagen und anbieten, es nachzureichen
- Komplexe Fragen: "Gute Frage, lass mich das genauer erklären..."
- Auf Handout verweisen: "Mehr Details dazu finden Sie im Handout"

### Schwierige Themen:
- OSI-Modell: Nicht zu tief einsteigen, nur die Idee vermitteln
- CIP: Den objektorientierten Ansatz als modern verkaufen
- Sicherheit: Das Thema ist ernst, aber lösbar
- Konkurrenz: Objektiv bleiben, nicht abwertend

---

## Mögliche Fragen und Antworten:

**F: Warum nicht gleich 5G in der Fabrik nutzen?**
A: 5G ist vielversprechend, aber EtherNet/IP ist kabelgebunden = zuverlässiger, keine Funkstörungen, deterministische Latenz. 5G wird eher als Ergänzung gesehen für mobile Geräte.

**F: Ist EtherNet/IP nicht langsamer als EtherCAT?**
A: Ja, aber für 90% der Anwendungen völlig ausreichend. EtherCAT ist Overkill für die meisten Fälle - wie einen Formel-1-Wagen für die Fahrt zum Supermarkt.

**F: Kann man EtherNet/IP und PROFINET mischen?**
A: Ja, über Gateways möglich. Aber besser ist es, sich für ein System zu entscheiden, um Komplexität zu reduzieren.

**F: Was ist mit TSN (Time-Sensitive Networking)?**
A: TSN ist die Zukunft - ermöglicht Hard-Realtime über Standard-Ethernet. EtherNet/IP wird TSN unterstützen. Dann können wir EtherCAT-Geschwindigkeit mit EtherNet/IP-Einfachheit kombinieren.

**F: Wie sicher ist EtherNet/IP gegen Hacker?**
A: Mit CIP Security sehr sicher. Wichtig ist Defense-in-Depth: Firewall + Segmentierung + Verschlüsselung. Sicherheit ist ein Prozess, keine Einmalinvestition.

**F: Warum nutzt Bosch nicht nur PROFINET (Siemens)?**
A: Bosch hat global Werke, in den USA ist EtherNet/IP Standard. Außerdem wollen wir nicht von einem Hersteller abhängig sein. Wir nutzen beides, je nach Standort und Anforderung.

---

## Wichtigste Botschaften (Top 5):

1. **EtherNet/IP = Ethernet für die Fabrik**
   - Standard TCP/IP + industrielle Intelligenz (CIP)

2. **Kosteneffizient & offen**
   - 0€ Lizenzgebühren, Standard-Hardware

3. **Einfache IT-Integration**
   - Webserver, Standard-Tools, Cloud-ready

4. **Für 90% der Anwendungen perfekt**
   - Nicht Ultra-High-Speed, aber mehr als ausreichend

5. **Zukunftssicher**
   - 30+ Mio. Knoten, Industrie 4.0, TSN-ready

---

Viel Erfolg bei deiner Präsentation!
