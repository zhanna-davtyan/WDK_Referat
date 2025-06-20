# CouchDB CIA World Factbook Analyse 

Dieses Projekt demonstriert die Migration und Analyse von Daten aus dem CIA World Factbook. Es nutzt eine CouchDB NoSQL-Datenbank, die über Docker ausgeführt wird, und führt die Analysen in Jupyter Notebooks durch, um sozioökonomische Muster zu identifizieren.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgende Software auf Ihrem System installiert ist:

* **Docker und Docker Compose:** Wird benötigt, um den CouchDB-Datenbankcontainer zu starten und zu verwalten.
    * Installationsanleitung: [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/)
* **Python:** Version 3.10 oder höher. Dieses Projekt wurde spezifisch mit Python 3.10 entwickelt und getestet.
    * Download: [https://www.python.org/](https://www.python.org/)

## Setup und Installation

1.  **Repository klonen (oder herunterladen):**
    ```bash
    git clone https://github.com/zhanna-davtyan/WDK_Referat.git
    cd WDK_REFERAT_DAVTYAN
    ```
    Alternativ kann das Repository auch als ZIP-Datei heruntergeladen und entpackt werden.

2.  **CouchDB-Container starten:**
    Öffnen Sie ein Terminal im Projekt-Hauptverzeichnis (wo die `docker-compose.yml` liegt) und führen Sie aus:
    ```bash
    docker-compose up -d
    ```
    Dieser Befehl lädt das CouchDB-Image herunter (falls noch nicht vorhanden) und startet den Container im Hintergrund (`-d` = detached mode).

    Alternativ können Sie die Oberfläche verwenden.

    Sie können auch oben in der docker-compose.yml auf „Run Service“ oder „Run All Services“ klicken.
    Das hat denselben Effekt wie der Terminal-Befehl.
   
    * Sie können überprüfen, ob CouchDB läuft, indem Sie im Browser auf `http://localhost:5984/_utils/` zugreifen. Loggen Sie sich mit dem Benutzernamen `admin` und Ihrem festgelegten Passwort ein.

    Um den CouchDB-Container zu stoppen und zu entfernen, ohne die gespeicherten Daten zu löschen, verwenden Sie:
    ```bash
    docker-compose down
    ```
    Um den Container zu stoppen und alle Daten zu löschen, verwenden Sie:
    ```bash
    docker-compose down -v
    ```
    *(Achtung: Dadurch gehen alle in CouchDB gespeicherten Daten verloren!)*
## Setup-Schritte für die Ausführung

Dieses Projekt verwendet eine virtuelle Umgebung (`venv`), um Projektabhängigkeiten zu isolieren.

1.  **Stellen Sie sicher, dass Python 3 installiert ist:**
    Öffnen Sie ein Terminal und prüfen Sie Ihre Python-Version:
    ```bash
    python3 --version
    ```
    *(Eine Version >= 3.10 wird empfohlen, da das Projekt damit entwickelt wurde. Neuere Versionen wie 3.11 oder 3.12 funktionieren wahrscheinlich ebenfalls.)*

2.  **Navigieren Sie zum Projektverzeichnis:**
    Wechseln Sie im Terminal in das Hauptverzeichnis dieses Projekts (wo sich diese README und die `requirements.txt` befinden).

3.  **Virtuelle Umgebung erstellen:**
    Erstellen Sie eine virtuelle Umgebung namens `.venv` mit Ihrem `python3`-Befehl:
    ```bash
    python3 -m venv .venv
    ```

4.  **Virtuelle Umgebung aktivieren:**
    * macOS / Linux: `source .venv/bin/activate`
    * Windows (Git Bash): `source .venv/Scripts/activate`
    * Windows (Cmd): `.venv\Scripts\activate.bat`
    * Windows (PowerShell): `.venv\Scripts\Activate.ps1`
    *(Der Terminal-Prompt sollte sich ändern und `(.venv)` am Anfang zeigen.)*

5.  **Benötigte Pakete installieren:**
    Installieren Sie alle notwendigen Bibliotheken aus der mitgelieferten `requirements.txt`-Datei:
    ```bash
    pip install -r requirements.txt
    ```

6.  **Notebooks ausführen:**
    
    1. JupyterLab starten:
    ```bash
    jupyter lab
    ```


