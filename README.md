# Alibi

Pitch link:
https://doenmezardastudents.github.io/Alibi/

# Alibi – Simple Excuse List

HTL-Schulprojekt (SYP, 4. Klasse). Dieses Repo enthält aktuell **nur die Pitch-Präsentation** (reveal.js), nicht die App selbst.

## Was ist das Projekt?
Eine digitale Entschuldigungsliste für Schulen als Web-App. Die Plattform verbindet WebUntis, Schüler, Eltern und Lehrer und ersetzt die klassische Zettelwirtschaft. Alibi gibt es schon, das Team baut es dieses Jahr sauberer und geplanter komplett neu.

### Das bisherige Problem
- Entschuldigungszettel gehen schnell verloren
- Unterschriften sind fälschbar oder schwer lesbar
- Lehrer haben viel Aufwand beim Kontrollieren und Eintragen
- Schüler und Eltern haben keine Übersicht über offene Fehlstunden

### Die Lösung
- **Automatisch:** Fehlzeiten werden direkt aus WebUntis importiert (offizieller API-Key ist angefragt).
- **100 % digital:** Kein Papier, kein Einscannen.
- **Einfach:** Eltern unterschreiben direkt am Handy, Tablet oder PC.

### Workflow
1. **Schüler – Einreichen:** Loggen sich ein, sehen ihre offenen Fehlzeiten aus WebUntis und leiten sie per „Einreichen“ an die Eltern weiter. In der Präsentation lädt der Schüler dabei einen Nachweis hoch, z. B. eine Arztbestätigung.
2. **Eltern – Unterschreiben:** Eigener Account, mit dem Kind verknüpft. Sehen alle offenen Anfragen und unterschreiben im Browser per Touchpad, Maus oder Finger (wie beim Paketempfang).
3. **Lehrer – Kontrollieren:** Übersicht über die ganze Klasse, sehen was schon unterschrieben ist, akzeptieren oder lehnen ab (z. B. wenn ein Attest fehlt). Dazu Statistiken: „Fehlt der Schüler oft montags?“, Fehlzeiten pro Schüler, offene/abgeschlossene Entschuldigungen.

### Geplanter Tech-Stack der App
Angular (Frontend), C# / ASP.NET Core (Backend), PostgreSQL (Datenbank).

## Repo-Aufbau
- `reveal.js/index.html` – die Präsentation (Deutsch, eigenes CSS im `<style>`-Block). Der Teil „Lösung“ ist ein vertikaler Folienstapel mit Unterfolien für Schüler, Eltern und Lehrer (inkl. Analyse).
- `reveal.js/pics/` – Bilder für die Folien (z. B. Foto der aktuellen Papier-Entschuldigungsliste).
- `.github/workflows/pages.yml` – deployt `reveal.js/` bei jedem Push auf `main` nach GitHub Pages: https://doenmezardastudents.github.io/Alibi/

## Arbeitsweise
- Mehrere Teammitglieder arbeiten zusammen und benutzen verschiedene Branches. Sie schauen keine Merchkonflikts zu haben.
