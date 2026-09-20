# FIB Akten-System — Starter

## Voraussetzungen
Node.js 18+ und npm.

## Start
1. ZIP entpacken und im Ordner Terminal öffnen.
2. `npm install`
3. `.env.example` als `.env` speichern und `SESSION_SECRET` durch einen langen zufälligen Wert ersetzen.
4. `npm start`
5. `http://localhost:3000` öffnen.

## Master-Zugang
Es gibt absichtlich kein fest eingebautes Standardpasswort. Der Master-Account wird beim ersten erfolgreichen Discord-OAuth-Login mit `MASTER_DISCORD_ID=1096326379064283218` automatisch angelegt. Deshalb zuerst Discord OAuth einrichten.

## Discord OAuth (optional)
Discord Developer Portal → Application → OAuth2. Als Redirect URL exakt `http://localhost:3000/auth/discord/callback` setzen. Client ID, Client Secret und Callback URL in `.env` eintragen. OAuth benötigt nur den Scope `identify`, keinen Bot-Token. Für den Internetbetrieb HTTPS verwenden und `COOKIE_SECURE=true` setzen.

## Enthalten
Dashboard, Akten erstellen/suchen/öffnen, Beweisregister mit Datei-Upload (max. 15 MB; PNG/JPG/PDF/TXT/MP4/WEBM/ZIP), Mitarbeiterverwaltung, Benutzeranlage, Rechteauswahl, Master Control und Audit-Log.

## Sicherheit
Dies ist ein RP-/Community-Starter, keine offizielle Behördenanwendung. Vor öffentlichem Einsatz unbedingt CSRF-Schutz, Rate-Limiting, strengere Rollenprüfung, Upload-Quarantäne/Validierung, HTTPS, sichere Backups und Tests ergänzen. Daten liegen lokal in `fib.sqlite`, `sessions.sqlite` und `uploads/`; diese nicht öffentlich teilen. Berechtigungen sind ein einfacher Ausgangspunkt und müssen vor produktivem Betrieb geprüft werden.
