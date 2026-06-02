# Purzelhuus Menüplaner Pro

Neue PWA für GitHub Pages und iPhone.

## Inhalt
- 250 Morgenessen
- 250 kompatible Mittagessen-Menügruppen
- 250 Z'Vieri
- Automatische Wochenplanung mit 2 Fleisch, 1 Fisch, 2 Vegi
- Morgenessen wird automatisch gefüllt
- Einkaufsliste
- Rezepte
- Eigene Menüs direkt in der App erfassen
- Export/Import der Datenbank

## GitHub Pages
ZIP entpacken und alle Einzeldateien ins Repository hochladen:
- index.html
- data.js
- sw.js
- manifest.webmanifest
- icon.svg
- purzelhuus-logo.jpeg

Nicht die ZIP-Datei hochladen.


## Version 11
- Suchfunktion pro Mahlzeit im Wochenplan ergänzt.
- Jedes Morgenessen, Mittagessen und Z'Vieri kann direkt per Suchfeld gefiltert werden.


## Version 12
- Word-Export als .doc ergänzt.
- PDF-/Druckansicht ergänzt.
- Mail-Vorbereitung an glenn.mueller9@me.com ergänzt.
- Hinweis: Automatische Mail mit Anhang braucht einen Server/Maildienst. GitHub Pages allein kann keine Anhänge direkt versenden.


## Version 13
- Buttons «Plan kopieren» und «CSV» entfernt.
- Instagram-Post als quadratisches PNG ergänzt.
- Wochenplan wird illustrativ im Purzelhuus-Stil zusammengefasst.


## Version 14
- Instagram-Export auf Story-Hochformat 1080 × 1920 angepasst.
- Design näher am Purzelhuus-Logo.
- Keine Sprüche im Bild.
- Menüs pro Wochentag chronologisch dargestellt.
- Texte in den Kästen mittig und besser lesbar.


## Version 15
- Automatische Migration alter lokaler Speicherstände ergänzt.
- Sucht nach purzelDataV10 bis V14 sowie alten purzelhuusMenus-Speichern.
- Führt alte Menüs und Rezepte ohne Dubletten mit der aktuellen Datenbank zusammen.
- Erstellt zusätzlich ein lokales Backup im Browser.
- Neuer Button im Exportbereich: «Alte Daten suchen & übernehmen».


## Version 16 Supabase
Diese Version ist mit Supabase verbunden:
- URL: https://uhizczhzbrtelaujhusk.supabase.co
- neue Menüs werden direkt in Supabase gespeichert
- beim Start lädt die App aus Supabase
- lokale Daten können unter Export in Supabase hochgeladen werden

### Einmaliges Zusatz-SQL in Supabase
Damit Upload/Upsert sauber funktioniert:

```sql
alter table morgenessen add constraint morgenessen_name_unique unique (name);
alter table mittagessen add constraint mittagessen_title_unique unique (title);
alter table zvieri add constraint zvieri_name_unique unique (name);
```

Falls eine Constraint bereits existiert, diese Meldung ignorieren.


## Version 17
- Masterdatenbank als `seeddata.js` integriert.
- Neuer Button im Exportbereich: «Masterdatenbank in Supabase übertragen».
- Bestehende gleichnamige Menüs werden übersprungen.
- Kein SQL-Kopieren auf dem iPhone nötig.
