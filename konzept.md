# 🌀 Nemos Alchemie — Browsergame Konzept

## 1. Vision

Ein **endloses, lukides Browsergame** in dem der Spieler als Alchemist durch abstrakte Traumwelten reist. Jede Welt ist ein lebendiges Puzzle aus Symbolen, Farben und Texturen — nie dieselbe Welt zweimal. Das Spiel wächst mit dem Spieler: je mehr er erkundet, desto tiefer wird die Welt.

**Vibe:** Surreal, meditativ, ein bisschen mystic. Wie ein Traum den man nicht vergessen kann.

---

## 2. Gameplay — Endloser Alchemist

### Kernloop
1. Spieler betritt eine **Traumwelt** (prozedural generiert)
2. Er entdeckt **Symbole** und **alchemistische Rezepte**
3. Er kombiniert, transformiert, erschafft
4. Jede Entdeckung öffnet **neue Welten** und **neue Fähigkeiten**
5. Endlos weiterspielen — kein konventionelles Ende

### Welten-Struktur
- **Ätherwelten** — Schwebende Inseln, Schwerkraft ist optional
- **Kristallhöhlen** — Reflektierende Wände, Licht als Mechanik
- **Traumstädte** — Verworrene Architektur, Zeit läuft anders
- **Ozeane ohne Wasser** — Atmosphäre als Mechanik
- **Der Fluss** — Kontinuierlich wachsende Weltkarte, niemals dieselbe Route

### Spielmechaniken
- **Symbol-Sammlung** — Gefundene Symbole werden im Grimoire festgehalten
- **Alchemie-Rezepte** — Kombinationen von Symbolen ergeben neue Elemente
- **Wachstum** — Spielerlevel erhöht Zugang zu neuen Welten
- **Persistenz** — Alles bleibt gespeichert; Webstorage oder Backend
- **OpenClaw-Events** — Tägliche/montliche Events die neue Inhalte bringen

### Endlosigkeit
- Prozedurale Generierung von Welten
- Algorithmisch wachsende Rezeptbäume
- Kein maximaler Level-Cap
- Seasons/Episodes als Wachstumsmarker

---

## 3. Technischer Stack

### Frontend
- **HTML5 + CSS3 + Vanilla JavaScript** — simpel, überall spielbar
- **Canvas API** — für prozedurale Grafik
- **LocalStorage** — für Spielstand-Speicherung (MVP)
- Optional: WebGL für Effekte

### Backend (später)
- Einfacher Node.js-Server für Multiplayer/Persistenz in der Cloud
- OpenClaw als Game-Master-Agent: steuert Events, generiert Quests
- Telegram-Bot-Integration: Spieler erhalten Benachrichtigungen über Events

### OpenClaw-Integration
- **Cron-Hooks** für tägliche Events
- **Telegram-Bot** für Benachrichtigungen und Spieler-Feedback
- **Agent als Dungeon Master** — OpenClaw generiert personalisierte Quests
- **Heartbeat** prüft Spielstände und generiert Belohnungen

---

## 4. Was das Spiel besonders macht

- **Lukide Atmosphäre** — Kein Fantasy-Klischee, keine Orks oder Elfen. Stattdessen: Traumwelten, Alchemie, Surrealismus
- **OpenClaw als Lebendigkeit** — Der Agent ist der Game Master der Welt
- **Endlos, aber bedeutungsvoll** — Jede Entdeckung fühlt sich wichtig an
- **Surrealer Vibe** — Inspiriert von: Aether S Lair, Animal Crossing Traumwelten, Alchemie-Symbolik

---

## 5. MVP — Erste Stufe (Schnell umsetzbar)

### Was es braucht
1. **Startscreen** mit Name-Eingabe
2. **Erste Ätherwelt** — 1 prozedural generierter Raum
3. **3-5 Symbole** zum Sammeln
4. **Grimoire** — Sammlung der gefundenen Symbole
5. **Speichern/Laden** via LocalStorage

### Zeitraum MVP
- Design: 1 Tag
- Entwicklung: 3-5 Tage
- Test: 1 Tag

### Danach
- Mehr Welten
- Telegram-Bot für Benachrichtigungen
- Rezept-System erweitern
- Agent-gesteuerte Quests

---

## 6. Nächste Schritte

1. **Design-Dokument** vertiefen (Symbol-Sprache, Farbpalette, Sound)
2. **Tech-Stack finalisieren** (Canvas vs. WebGL)
3. **MVP scope definieren** und losprogrammieren
4. **OpenClaw-Integration** planen (Events, Telegram-Bot)

---

*Konzept erstellt: 2026-04-07*
*Status: Brainstorm — Bereit für Vertiefung*
