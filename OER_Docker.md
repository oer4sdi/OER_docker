# Einführung in Docker


### Was ist Docker und wo findet es in Spatial Information Infrastructures (SDI) Anwendung?

Docker ist eine leistungsstarke Container-Plattform, die es ermöglicht, Anwendungen in isolierten Umgebungen zu betreiben. Dies ist besonders hilfreich, wenn Anwendungen gleiche Software-Voraussetzungen benötigen. Ein Docker-Container enthält alle nötigen Abhängigkeiten, Bibliotheken und Software, die für den Betrieb einer Anwendung erforderlich sind.
> [!NOTE]
> In **Spatial Data Infrastructures (SDI)** wird Docker genutzt, um geographische Anwendungen wie QGIS, GeoServer oder Jupyter Notebooks einfach und konsistent zu installieren. 
Dadurch lassen sich komplexe Umgebungen schnell bereitstellen und unabhängig vom Host-System betreiben, was die Verwaltung und Skalierbarkeit erleichtert.

### Docker-Grundlagen: Dockerfile, Docker Image und Container


Damit Anwendungen auf jedem Endgerät problemlos laufen, sind einige technische Voraussetzungen notwendig. Docker ist ein Open-Source-Tool, das es ermöglicht, Anwendungen in `isolierten Containern` auszuführen. Diese `Container` enthalten alles, was die Anwendung benötigt – Code, Laufzeit, Bibliotheken und Konfigurationen – und sorgen dafür, dass sie unabhängig vom Host-System - dem Endgerät - einheitlich funktioniert.
` Container` basieren auf `Docker Images`, die als Vorlage oder Bausatz dienen und alle notwendigen Elemente enthalten. Die Erstellung eines `Docker Images` erfolgt über eine `Dockerfile`, eine einfache Textdatei, die Anweisungen und Befehle enthält. Docker erleichtert so die Entwicklung, Bereitstellung und Skalierung von Software auf verschiedenen Systemen.

[//]: # (Video-embedding und hochladen: Videos können entweder, wie in der nächsten Zeile exemplarisch zu sehen, verlinkt werden, oder direkt hochgeladen werden. Für direktes Hochladen sieht die Syntax in etwa so aus: <video src="https:videolink.mp4"></video>)
[![Docker - schnell erklärt!](https://github.com/user-attachments/assets/198489d5-0acd-425a-bb36-4427b44cfa8c)](https://av.tib.eu/media/68592)


**Selbsttest 1: Docker Grundlagen**

**Frage 1:** Wofür wird Docker primär genutzt?

- [ ] a. Zum Erstellen von virtuellen Maschinen  
- [x] b. Zur Erstellung isolierter Container, die Softwareumgebungen enthalten  
- [ ] c. Zur Verwaltung von Netzwerken  
- [ ] d. Zum Schreiben von Programmen  

**Frage 2:** Welche Funktion erfüllt Docker beim Betrieb von Geoservern?

- [ ] a. Es sorgt für bessere Datenvisualisierung  
- [x] b. Es stellt sicher, dass der Geoserver von unterschiedlichen Systemen erreichbar ist  
- [ ] c. Es ermöglicht es, Webdienste im Netzwerk zugänglich zu machen  
- [ ] d. Es führt automatische Software-Updates durch  

**Frage 3:** Was ist ein Docker Image?

- [ ] a. Ein Container, der läuft  
- [ ] b. Eine virtuelle Maschine  
- [x] c. Eine Vorlage, die Anweisungen für die Erstellung von Containern enthält  
- [ ] d. Ein Netzwerk-Tool  

**Frage 4:** Was ist ein Docker Container?

- [x] a. Eine isolierte Instanz, die auf einem Docker Image basiert  
- [ ] b. Eine Software, die Netzwerke verwaltet  
- [ ] c. Eine Anwendung zum Verwalten von Code  
- [ ] d. Eine virtuelle Maschine  

**Frage 5:** Was passiert beim Befehl *docker build* im Zusammenhang mit einem Docker file?

- [ ] a. Es wird eine virtuelle Maschine erstellt  
- [ ] b. Es wird ein Docker Container gestartet  
- [x] c. Es wird ein Docker Image erzeugt  
- [ ] d. Es wird eine neue Netzwerkkonfiguration eingerichtet  
___
# Praktische Anwendung: Docker für Jupyter Notebook

**Jupyter Notebook** (bzw. Jupyter Lab) ist eine web-basierte Programmierumgebung, die sich für die geographische Datenanalyse mit Python eignet. **Docker ermöglicht es, Jupyter mit allen notwendigen Modulen zur räumlichen Analyse in einem Container zu installieren.** Beispielsweise kann das Docker-Image `darribas/gds_py:10.0` verwendet werden, um eine komplette Umgebung für die geographische Analyse einzurichten.
#### [Docker Image Darribas](https://hub.docker.com/r/darribas/gds_py)

[![Docker - Ein Praxisbeispiel mit Jupyter Notebook!](https://github.com/user-attachments/assets/9c201f4c-5791-4ad6-8c94-2e26968b17f2)](https://av.tib.eu/media/68594)


### Beispielprojekt: Visualisierung von COVID-19-Fällen
![COVID-19 Visualisierung mit Docker & Jupyter Notebook](https://github.com/user-attachments/assets/aebc3447-a2df-43fc-9aa0-d0ca64cd0111)

**Arbeitsschritte**
1. Die [WHO Daten](https://data.who.int/dashboards/covid19/data?n=c) zu COVID-19-Fällen werden in Jupyter Notebook geladen.
2. Ein zusätzlicher Datensatz zu den Staatsgrenzen wird importiert (z.B. `naturalearth_lowres`). [Natural Earth](https://www.naturalearthdata.com/downloads/)
3. Die beiden Datensätze werden mithilfe von `pandas` und `geopandas` zusammengeführt und auf einer Karte dargestellt.

Ein praktisches Beispiel ist die Visualisierung von COVID-19-Daten. 
Die WHO stellt aktuelle Daten zu Infektionszahlen zur Verfügung, die mit Modulen wie pandas und geopandas in Jupyter Notebook bearbeitet werden können. 
Ergänzt werden diese durch räumliche Daten, etwa die Staatsgrenzen aus dem Datensatz naturalearth_lowres.
Nach dem Import beider Datensätze können sie durch den Befehl pd.merge kombiniert und anschließend als Karte visualisiert werden. 
Docker sorgt hierbei dafür, dass alle benötigten Tools ohne manuelle Installation einsatzbereit sind.

WHO COVID-19 Data          |  Natural Earth Datensatz
:-------------------------:|:-------------------------:
![](https://github.com/user-attachments/assets/29573a76-ed92-4def-97bd-68687b826a4c)  |  ![](https://github.com/user-attachments/assets/92919e07-8071-4c73-a77c-ab790b1d9368)

merging dataset          |  Plot of COVID-19 and natural earth data
:-------------------------:|:-------------------------:
![](https://github.com/user-attachments/assets/b837d404-314b-4f2a-8436-0bcee6fbb169)  |  ![](https://github.com/user-attachments/assets/5d8263a4-da28-4616-bc88-7255e3a886fe)



### Selbsttest Part 2


**Frage 1:** Was ist der Vorteil von Docker beim Einsatz von Jupyter Notebook / Jupyter Lab?

- [ ] a. Es ermöglicht eine schnellere Datenverarbeitung  
- [x] b. Es stellt sicher, dass alle nötigen Module zur Verfügung stehen, ohne sie manuell zu installieren  
- [ ] c. Es erhöht die Sicherheit von Jupyter Notebook  
- [ ] d. Es verbessert die Visualisierung der Daten  

**Frage 2:** Welcher Befehl lädt das Docker-Image für die räumliche Analyse?

- [ ] a. `docker run darribas/gds_py:10.0`  
- [ ] b. `docker build darribas/gds_py:10.0`  
- [x] c. `docker pull darribas/gds_py:10.0`  
- [ ] d. `docker start darribas/gds_py:10.0`  

**Frage 3:** Welche Module sind notwendig, um geographische Daten in Jupyter Notebook zu verarbeiten?

- [ ] a. numpy und scipy  
- [x] b. pandas und geopandas  
- [ ] c. matplotlib und seaborn  
- [ ] d. flask und django  

## Evaluation und Abschluss

In dieser Einheit haben wir die Grundlagen von Docker sowie dessen Anwendung im geographischen Kontext besprochen. Docker ermöglicht es, komplexe Softwareumgebungen wie Jupyter Notebook mit allen nötigen Abhängigkeiten schnell und effizient bereitzustellen. Die Verwendung von Docker spart Zeit und minimiert technische Schwierigkeiten, indem es eine einheitliche Arbeitsumgebung für alle Nutzer bereitstellt.
