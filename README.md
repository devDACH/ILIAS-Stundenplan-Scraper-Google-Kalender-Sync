# ILIAS-Stundenplan-Scraper-Google-Kalender-Sync-
ILIAS Stundenplan Scraper (Google Kalender Sync) 

# Anleitung: Google Kalender Sync für den Stundenplan Scraper

Google Cloud Console öffnen

Öffne: https://console.cloud.google.com

---------------------------------------------------------------------------

## 2. Neues Projekt erstellen

* Oben auf „Projekt auswählen“
* „Neues Projekt“
* Beliebigen Namen vergeben (z. B. `Stundenplan Sync`)
* Projekt erstellen

----------------------------------------------------------------------------

## 3. Google Calendar API aktivieren

Öffne:
https://console.cloud.google.com/apis/library/calendar-json.googleapis.com
Dann:
* „Aktivieren“

-----------------------------------------------------------------------------
## 4. OAuth Consent Screen konfigurieren
Öffne:
https://console.cloud.google.com/apis/credentials/consent
Dann:
* „External“ auswählen
* App Name eintragen (z. B. `Stundenplan Sync`)
* Eigene E-Mail-Adresse eintragen
* Speichern

-------------------------------------------------------------------------------

## 5. OAuth Client erstellen
Öffne:
https://console.cloud.google.com/apis/credentials
Dann:
* „Create Credentials“
* „OAuth Client ID“
* Typ: `Desktop App`
Anschließend:
* JSON-Datei herunterladen

-----------------------------------------------------------------------------

## 6. Datei umbenennen
Die heruntergeladene Datei (z. B. `client_secret_xxxxx.json`) umbenennen zu:
credentials.json

------------------------------------------------------------------------------
## 7. Datei in den Projektordner legen

Die Datei muss im selben Ordner liegen wie das Python-Script bzw. die EXE:

ScraperAndroid.py
credentials.json

oder später:
Scraper.exe
credentials.json

------------------------------------------------------------------------------

## 8. Benötigte Python-Pakete installieren
Im Terminal/CMD ausführen:

pip install google-api-python-client google-auth-httplib2 google-auth-oauthlib

--------------------------------------------------------------------------------

## 9. Google Kalendername in der GUI eintragen

Im Feld:
Google Kalendername

z. B.: Stundenplan
eintragen.

Falls der Kalender noch nicht existiert, erstellt das Tool ihn automatisch.

-------------------------------------------------------------------------------

## 10. Erster Sync

Beim ersten Synchronisieren:

* Browser öffnet sich automatisch
* Mit Google anmelden
* Zugriff erlauben
  
Danach wird automatisch gespeichert:

output/google_token.json

-----------------------------------------------------------------------------------

## Ilias Login / Pfadeingabe 

Bei Ilias Stundenplan Ordner Link den Link angeben, aus dem die Stundenpläne gescrapt werden sollen

Benutzername und Passwort müssen außerdem hinterlegt werden

## Scraper Buttons 

der Scraper hat 2 Buttons: 
Button 1: Scrape and Convert Stundenpläne --> Hier erfolgt der Download und die Konvertierung aller im Ilias Ordner gefundenen Stundenpläne 
Button 2: Hier erfolgt der Sync zum Google Kalender.

Alternativ kann die ICS Datei die in Schritt 1 erstellt wird auch manuell eingepflegt werden


Wenn diese Vorbereitung abgeschlossen ist kann über den Scraper mit den gesetzen ILIAS und Google Kalender Daten der Stundenplan direkt in den Google Kalender gesynct werden

Ab dann funktioniert der Sync automatisch ohne erneute Anmeldung.
