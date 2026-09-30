# Project Proposal – Alibi

**Projekt:** Alibi – Digitale Entschuldigungsliste für Schulen
**Fach:** SYP (Systementwicklungsprojekt), 4. Klasse HTL
**Datum:** 30.09.2026
**Team:** Arda Dönmez, Daryan Mamsaleh, Ernad Music, Lorenz Parzer
> Diese Proposal folgt der Struktur der Vorlage `Unit02a_ProjectProposalPresentation.pptx`.

---

## Zweck dieses Dokuments

Dieses Project Proposal dient als Entscheidungsgrundlage für die Genehmigung des Projekts *Alibi*. Es beschreibt:

- die **Notwendigkeit** des Projekts
- die **Machbarkeit** des Projekts
- die **Finanzierbarkeit** des Projekts
- den **Markt- und wirtschaftlichen Effekt** des Projekts

## Inhaltsverzeichnis

1. [Ausgangssituation](#1-ausgangssituation)
2. [Rahmenbedingungen und Einschränkungen](#2-rahmenbedingungen-und-einschränkungen)
3. [Projektziele und Systemkonzept](#3-projektziele-und-systemkonzept)
4. [Chancen und Risiken](#4-chancen-und-risiken)
5. [Planung](#5-planung)
6. [Wirtschaftlichkeit](#6-wirtschaftlichkeit)

---

## 1. Ausgangssituation

Schulen verwalten Entschuldigungen für Fehlzeiten von Schüler:innen aktuell größtenteils über **Papierzettel**. Dieser Prozess ist zeitaufwändig und fehleranfällig:

- Entschuldigungszettel **gehen schnell verloren** (auf dem Schulweg, im Ranzen, im Lehrerzimmer).
- Unterschriften sind **fälschbar oder schwer lesbar** – eine echte Kontrolle der Echtheit ist praktisch nicht möglich.
- Lehrer:innen haben **viel manuellen Aufwand** beim Kontrollieren, Sammeln und Eintragen der Zettel in WebUntis.
- Schüler:innen und Eltern haben **keine digitale Übersicht**, welche Fehlstunden noch offen bzw. unentschuldigt sind.

Ein Vorgängerprojekt namens *Alibi* existiert bereits, ist aber technisch und konzeptionell nicht sauber genug umgesetzt. Das aktuelle Team plant daher einen **kompletten Neuaufbau**, diesmal mit klarer Planung und sauberer Architektur.

**Gap:** Es fehlt eine zentrale, digitale Plattform, die WebUntis-Fehlzeiten automatisch mit einem einfachen, rechtssicheren Unterschriften- und Freigabeprozess zwischen Schüler:innen, Eltern und Lehrer:innen verbindet.

## 2. Rahmenbedingungen und Einschränkungen

### Organisatorisch
- Schulprojekt im Rahmen des SYP-Unterrichts (4. Klasse HTL), fixe Deadlines durch den Lehrplan.
- Mehrere Teammitglieder arbeiten parallel in unterschiedlichen Git-Branches (Merge-Konflikte werden aktiv vermieden).
- Kein Budget notwendig.

### Technisch
- Geplanter Tech-Stack:
  - **Frontend:** Angular
  - **Backend:** C# / ASP.NET Core
  - **Datenbank:** PostgreSQL
- Anbindung an **WebUntis** ist zentral für das Projekt – ein offizieller API-Key wurde bereits angefragt, liegt aber noch nicht vor. **Risiko:** Verzögerung, falls der Key nicht rechtzeitig verfügbar ist (siehe Kapitel 4).
- Deployment/Hosting der Präsentation erfolgt bereits über GitHub Pages (`reveal.js/` → CI via GitHub Actions); die eigentliche App benötigt noch ein eigenes Hosting-/Deployment-Konzept.

### Rechtlich / Datenschutz
- Es werden **sensible personenbezogene Daten** von minderjährigen Schüler:innen verarbeitet (Fehlzeiten, ggf. Krankheitsnachweise). Eine **DSGVO-konforme** Umsetzung ist Pflicht.
- Digitale Unterschriften der Eltern müssen im schulischen/rechtlichen Kontext ausreichend nachvollziehbar/verbindlich sein.

## 3. Projektziele und Systemkonzept

**Vision:** *Alibi* ersetzt die klassische Papier-Entschuldigungsliste durch einen durchgängig digitalen, einfachen und automatisierten Workflow zwischen Schule, Schüler:innen und Eltern.

**Kernprinzipien:**
- **Automatisch:** Fehlzeiten werden direkt aus WebUntis importiert – keine manuelle Doppelerfassung.
- **100 % digital:** Kein Papier, kein Einscannen von Zetteln.
- **Einfach:** Eltern unterschreiben direkt am Handy, Tablet oder PC – ähnlich der Unterschrift bei einer Paketzustellung.

**Workflow (grob, ohne technische Details):**

1. **Schüler:in – Einreichen**
   Loggt sich ein, sieht die eigenen offenen Fehlzeiten aus WebUntis und leitet sie per „Einreichen" an die Eltern weiter. Optional wird dabei ein Nachweis (z. B. Arztbestätigung) hochgeladen.

2. **Eltern – Unterschreiben**
   Eigener Account, verknüpft mit dem Kind. Eltern sehen alle offenen Anfragen und unterschreiben direkt im Browser per Touchpad, Maus oder Finger.

3. **Lehrer:in – Kontrollieren**
   Übersicht über die gesamte Klasse: Welche Entschuldigungen sind bereits unterschrieben? Lehrer:innen akzeptieren oder lehnen ab (z. B. bei fehlendem Attest). Zusätzlich stehen Statistiken zur Verfügung, z. B. „Fehlt der Schüler oft montags?", Fehlzeiten pro Schüler:in, offene/abgeschlossene Entschuldigungen.

Dieses Konzept bringt uns vom aktuellen Zustand (Papierzettel, manuelle Kontrolle) zum gewünschten Zustand (durchgängig digitaler, nachvollziehbarer Prozess) aus Kapitel 1.

## 4. Chancen und Risiken

### Chancen
- **Zeitersparnis für Lehrer:innen:** Deutliche Reduktion des Verwaltungsaufwands beim Sammeln, Kontrollieren und Eintragen von Entschuldigungen.
- **Bessere Übersicht:** Schüler:innen, Eltern und Lehrer:innen sehen jederzeit den aktuellen Stand offener Fehlzeiten.
- **Weniger Fälschungen/Streitfälle:** Digitale, nachvollziehbare Unterschriften statt leicht fälschbarer Zettel.
- **Skalierbarkeit:** Das System lässt sich potenziell auf mehrere Schulen ausrollen (nicht nur die eigene HTL), sofern WebUntis dort ebenfalls im Einsatz ist.

### Risiken
- **Abhängigkeit von WebUntis:** Der offizielle API-Key wurde angefragt, liegt aber noch nicht vor. Ohne API-Zugriff ist der automatische Import nicht umsetzbar → Fallback/Zeitplan-Risiko.
- **Datenschutz:** Fehlerhafte Umsetzung beim Umgang mit sensiblen Schülerdaten (Krankheitsnachweise etc.) kann rechtliche Probleme verursachen.
- **Akzeptanz:** Eltern und Lehrer:innen müssen die neue digitale Lösung tatsächlich nutzen wollen (Technologie-Skepsis, wie z. B. bei älteren Lehrkräften).
- **Team-/Zeitrisiko:** Als Schulprojekt mit fixem Abgabetermin und mehreren parallel arbeitenden Teammitgliedern besteht das Risiko von Zeitdruck und Merge-Aufwand gegen Ende.

## 5. Planung

### Grobe Meilensteine
| Meilenstein | Geplanter Termin |
|---|---|
| Projektstart | 22.09.2026 |
| Fertigstellung Grobkonzept/Proposal | 29.09.2026 |
| Erster klickbarer Prototyp | 13.10.2026 |
| Fertigstellung Backend-Grundfunktionen | unbeakannt |
| Fertigstellung Frontend-Grundfunktionen | unbekannt |
| Integrationstests | unbekannt |
| Projektabgabe/-ende | Anfang 2028 |

### Rollen im Team
| Rolle | Person |
|---|---|
| Projektleitung | Arda Dönmez |
| Backend-Verantwortung (ASP.NET Core) | Ernad und Daryan |
| Frontend-Verantwortung (Angular) | Arda |
| Datenbank-Verantwortung (PostgreSQL) | Lorenz |
| Dokumentation/Präsentation | Arda |

### Ressourcenbedarf
- **Personal:** 4 Teammitglieder pro 5h die Woche
- **Lizenzen/Tools:** Hosting, WebUntis API Key, Domain

## 6. Wirtschaftlichkeit

Da es sich um ein **Schulprojekt ohne kommerziellen Rahmen** handelt, steht die klassische Kosten-Nutzen-Rechnung nicht im Vordergrund. Dennoch lässt sich der Nutzen qualitativ abschätzen:

- **Nutzen für Lehrer:innen:** Zeitersparnis bei Verwaltungsaufgaben (weniger manuelle Kontrolle/Eintragung von Entschuldigungen).
- **Nutzen für Schule:** Bessere Datenqualität und Nachvollziehbarkeit von Fehlzeiten, weniger Papierverbrauch.
- **Kosten:** Entwicklungsaufwand ist im Rahmen des SYP-Unterrichts bereits "eingepreist" (Ausbildungszeit); laufende Kosten würden im Realbetrieb v. a. durch **Hosting** und ggf. eine **WebUntis-API-Lizenz** entstehen.
- **Perspektive für Realbetrieb:** Bei erfolgreichem Pilotbetrieb an der eigenen Schule wäre ein Rollout an weiteren Schulen mit WebUntis-Anbindung denkbar – dies würde eine genauere Wirtschaftlichkeitsrechnung (Hosting-Kosten pro Schule, Wartungsaufwand, ggf. Lizenzmodell) erfordern.


---
