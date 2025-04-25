# CouchDB CIA World Factbook Analyse 

Dieses Projekt dient der Analyse von Daten aus dem CIA World Factbook unter Verwendung von Python und einer CouchDB NoSQL-Datenbank, die mittels Docker ausgeführt wird. Es wurde im Rahmen eines Referats erstellt.

Das Projekt umfasst Skripte zum Laden der Factbook-Daten in die CouchDB-Datenbank und anschließende Analyse-Skripte mittels Jupyter Notebooks.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgende Software auf Ihrem System installiert ist:

* **Docker und Docker Compose:** Wird benötigt, um den CouchDB-Datenbankcontainer zu starten und zu verwalten.
    * Installationsanleitung: [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/)
* **Python:** Version 3.10 oder höher. Dieses Projekt wurde spezifisch mit Python 3.10 entwickelt und getestet.
    * Download: [https://www.python.org/](https://www.python.org/)
* **Git:** (Optional, aber empfohlen) Zum Klonen des Repositories.

## Setup und Installation

1.  **Repository klonen (oder herunterladen):**
    ```bash
    git clone https://github.com/zhanna-davtyan/WDK_Referat.git
    cd WDK_REFERAT_DAVTYAN
    ```
    Alternativ kann das Repository auch als ZIP-Datei heruntergeladen und entpackt werden.

2.  **CouchDB Passwort konfigurieren:**
    * **WICHTIG:** Öffnen Sie die Datei `docker-compose.yml`. Ändern Sie den Wert bei `COUCHDB_PASSWORD` von `SicheresPasswort` zu einem eigenen, sicheren Passwort.
    

3.  **CouchDB-Container starten:**
    Öffnen Sie ein Terminal im Projekt-Hauptverzeichnis (wo die `docker-compose.yml` liegt) und führen Sie aus:
    ```bash
    docker-compose up -d
    ```
    Dieser Befehl lädt das CouchDB-Image herunter (falls noch nicht vorhanden) und startet den Container im Hintergrund (`-d`).
    * Sie können überprüfen, ob CouchDB läuft, indem Sie im Browser auf `http://localhost:5984/_utils/` zugreifen. Loggen Sie sich mit dem Benutzernamen `admin` und Ihrem festgelegten Passwort ein.

4.  **Python Virtual Environment erstellen:**
    Es wird dringend empfohlen, eine virtuelle Umgebung zu verwenden, um Abhängigkeiten zu isolieren. Führen Sie im Projekt-Hauptverzeichnis aus:
    ```bash
    python3.10 -m venv .venv
    ```
    *(Hinweis: Je nach Systemkonfiguration lautet der Befehl möglicherweise nur `python` anstelle von `python3.10`)*.
    Dies erstellt einen Ordner `.venv` mit der isolierten Python-Umgebung.

5.  **Virtuelle Umgebung aktivieren:**
    * **macOS / Linux:**
        ```bash
        source .venv/bin/activate
        ```
    * **Windows (cmd/powershell):**
        ```bash
        .venv\Scripts\activate
        ```
    Der Terminal-Prompt sollte sich ändern und `(.venv)` anzeigen.

6.  **Python-Abhängigkeiten installieren:**
    Installieren Sie alle benötigten Python-Pakete mit pip innerhalb der aktivierten Umgebung:
    ```bash
    pip install -r requirements.txt
    ```

