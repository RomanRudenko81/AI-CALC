# Webex CC AI Unit Calculator

Statischer Presales-Calculator für:

- Webex AI Agent – Scripted Voice
- Webex AI Agent – Autonomous Voice
- Webex AI Agent – Scripted Digital
- Webex AI Agent – Autonomous Digital
- Webex AI Assistant – Voice
- Webex AI Assistant – Digital

Die Anwendung besteht nur aus `index.html` (HTML/CSS/JavaScript) und benötigt kein Backend.

## GitHub Pages Deployment

1. Neues GitHub Repository anlegen, z. B. `webex-ai-calculator`.
2. `index.html` in das Root-Verzeichnis des Repositories hochladen.
3. In GitHub: **Settings → Pages**.
4. Unter **Build and deployment** `Deploy from a branch` auswählen.
5. Branch `main`, Ordner `/ (root)` auswählen und speichern.
6. Nach kurzer Zeit zeigt GitHub die öffentliche Pages-URL an.

## Standard-Metering im Calculator

Stand August 2026:

| Workload | Kapazität pro Unit |
|---|---:|
| Scripted Voice | 1.600 Minuten |
| Autonomous Voice | 250 Minuten |
| Scripted Digital | 4.800 Sessions |
| Autonomous Digital | 200 Sessions |
| AI Assistant Voice | 2.000 Minuten |
| AI Assistant Digital | 12.000 Sessions |

Für **AI Agent Digital** wird gemäß der bereitgestellten aktuellen Bundle-Folie mit **10 Outbound Messages pro Client = 1 Session** und einem **24-Stunden-Sessionfenster** gerechnet. Für **AI Assistant Digital** wird die Anzahl der Digital Sessions direkt eingegeben. Die Werte können im Bereich **Erweiterte Lizenzannahmen** geändert werden.

## Wichtige Logik

AI Agent ist ein gemeinsamer Unit-Pool. Der Calculator addiert deshalb die Teilverbräuche als Unit-Äquivalente:

```text
AI Agent Units =
  Scripted Voice Minuten / 1600
+ Autonomous Voice Minuten / 250
+ Scripted Digital Sessions / 4800
+ Autonomous Digital Sessions / 200
```

AI Assistant wird analog berechnet:

```text
AI Assistant Units =
  Voice Minuten / 2000
+ Digital Sessions / 12000
```

Danach wird der optionale Sizing-Puffer angewandt und auf volle Units aufgerundet. Der Standardwert für den Puffer ist 0 %.

## Quellenbasis

Die Standardwerte wurden auf die im Chat bereitgestellten aktuellen Cisco-Bundle-Folien aktualisiert:

- AI Agent Bundle: $100 / Unit; Scripted Voice 1.600 Min.; Autonomous Voice 250 Min.; Scripted Digital 4.800 Sessions; Autonomous Digital 200 Sessions; 10 Outbound Messages pro Client = 1 Session; 24 Stunden Session Expiration.
- AI Assistant Bundle: $30 / Unit; Voice 2.000 Min.; Digital 12.000 Sessions.

Kann Richtigkeit nicht garantieren – bitte vor Angebotsabgabe aktuelle Cisco-Dokumentation, Vertragsbedingungen und CCW verifizieren.
