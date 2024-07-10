![[PLICON.svg]]
Portfolioland ist eine Präsentationsplattform für Studierende der Kunsthochschule Kassel.
Hier können sie ihre Arbeiten strukturieren, sortieren, kategorisieren, teilen und einem breiteren Publikum präsentieren. 
Die Arbeiten auf Portfolioland sind vielfältig und spiegeln die Kreativität und das Talent der Studierenden wider. Ob Gemälde, Skulpturen, Installationen oder digitale Medien – Portfolioland bietet den Studierenden einen Raum, ihre Fähigkeiten zu zeigen und sich mit einem breiteren Publikum zu vernetzen.

Portfolioland wurde von 2022 bis 2024 im Rahmen des Drittmittelprojektes "**Universität Kassel digital: Universitäre Lehre neu gestalten** - Teilprojekt A1.5 digitale Protfolio- und Ausstellungsformate" an der Kunsthochschule Kassel und der Universität Kassel aktiv entwickelt. Gefördert wurde das Projekt durch die Stiftung "Innovation in der Hochschullehre".

Die Software besteht aus zwei Teilen, dem Frontend und dem Backend. Das Frontend wurde in [[0002_Tools/Tools/Svelte/Sveltekit|Sveltekit]] geschrieben. Das Backend basiert auf [[0001_Entwicklung/0002_Development/0002_Dependencies/Pocketbase|Pocketbase]].

Die Software ist unter CC by lizensiert und verfügbar unter https://github.com/portfolioland/

**Funktionen**
- **Benutzerfreundliche Oberfläche:** Einfach zu navigierende Oberfläche zum Erstellen und Verwalten von Portfolios.
- **Sicher und privat:** Optionen zur Kontrolle der Privatsphäre und Sicherheit deines Portfolios.

## **Erste Schritte mit der Software**
### **Voraussetzungen**
Um Portfolioland lokal auszuführen, müssen folgende Programme auf deinem Rechner installiert sein:
- Node.js (v14 oder höher)
- npm

### **Installation**
Klonen des Repositories:

```bash
git clone https://github.com/portfolioland/portfolioland.git
cd portfolioland
```

Eine Dotenv-Datei `.env` mit folgenden Parameter muss in `./Frontend` bereitgestellt werden.

```env
PB_URL ="http://127.0.0.1:8090/"
PUBLIC_PB_URL ="http://127.0.0.1:8090/"
PUBLIC_TEST_ACCOUNT ="test@test.com"
PUBLIC_TEST_ACCOUNT_PW ="4MPzan1N6PONYa0"
REGISTERPW = "register"
```

Für lokalen Betrieb den Entwicklungsserver starten:
Führe die Pocketbase-Instanz aus:

```bash
cd ./Backend/Portfolio-Backend-pocketbase_0.20.0_darwin_arm64
./pocketbase serve
```

Stelle sicher, dass Pocketbase läuft. Das Pocketbase-Adminpanel sollte unter `http://localhost:8090/_` erreichbar sein.

Ausführen des Frontends

```bash
cd /Frontend
npm install
npm run dev
```

Öffnen Sie Ihren Browser und navigieren Sie zu:

```
http://localhost:5713
```

Nun sollten Sie die Portfolioland-Anwendung lokal laufen sehen.

![[Pasted image 20240627134225.png]]

**Nutzung**
1. **Konto erstellen:** Registrieren Sie sich mit Ihrer E-Mail oder über soziale Medien.
2. **Profil einrichten:** Fügen Sie persönliche Details, ein Profilbild und eine Biografie hinzu.
3. **Projekte hinzufügen:** Laden Sie Ihre Kunstwerke, Projekte und andere kreative Arbeiten hoch. Geben Sie Beschreibungen, Mediendateien und andere relevante Details an.
4. **Veröffentlichen und teilen:** Sobald Ihr Portfolio fertig ist, veröffentlichen Sie es und teilen den Link mit anderen.
## Technische Entscheidungen
Portfolioland wurde mit Hinblick auf einen Opensource-Gedanken entwickelt. Jede genutzte Software und Library ist unter einer der Opensource-Lizenzen veröffentlicht. Ebenso wird Portfolioland frei zugänglich sein. 
Das Repository ist in zwei Bereiche aufgeteilt. Dies ermöglicht es im Nachhinein die einzelnen Komponenten einfacher auszutauschen zu können.
Ein wichtiger Punkt war es die Software möglichst Transparent zu gestalten, die Daten die in sie zukünftig eingespeist werden, jedoch in eigener Hand zu behalten. Daher wurde sich in der Nutzung des [[Backend]]s für [[0001_Entwicklung/0002_Development/0002_Dependencies/Pocketbase|Pocketbase]] entschieden, das sich auf einem eigenen Server hosten lässt. 
Es wurde sich gegen Could-[[Database|Datenbank]]en wie  [[mongoDB]]-Atlas, oder die Cloudvariante von [[Supabase]] entschieden. 
Supabase ist in der selbst-gehosteten Variante eine Kandidatin, den Funktionsumfang der Software um eine [[SAML-Protokol|SAML]]-Schnittstelle zu erweitern. 
# Features:
![[02_Feature-List]]

# Roadmap
![[03_Roadmap]]