# Game Test-Checkliste

## Vor jedem Commit (mvp/index.html → game/index.html)

### 1. Frischer State (Cache leeren)
```
Hard Refresh: Ctrl+Shift+R (Windows) / Cmd+Shift+R (Mac)
```
**ODER** Browser DevTools → Network → "Disable cache" → Refresh

### 2. Tutorial Test (5 Steps)
- [ ] Name eingeben → "Betrete die Alchemie"
- [ ] Tutorial Step 1: "Willkommen" erscheint
- [ ] "Weiter" → Step 2
- [ ] "Weiter" → Step 3
- [ ] "Weiter" → Step 4
- [ ] "Weiter" → Step 5
- [ ] "Los geht's!" → Spiel startet

### 3. Basis-Funktionen
- [ ] WASD/ Pfeile: Avatar bewegt sich
- [ ] Symbol erscheint → Avatar sammelt es automatisch
- [ ] HUD zeigt Name + Level + XP
- [ ] Grimoire Button: Öffnet/Schliesst Overlay
- [ ] Biome Button: Wechselt Biome (IGNIS/AQUA/TERRA/AETHER)

### 4. SAVE/LOAD Test
- [ ] Ein Symbol einsammeln
- [ ] F5 / Refresh drücken
- [ ] Spielstand wird geladen (Symbole, XP, Level)
- [ ] Alles korrekt wiederhergestellt

### 5. Tier-Aufstieg Test
- [ ] Genug XP sammeln für Level 2
- [ ] Level-Up Notification erscheint
- [ ] Neue Symbole werden freigeschaltet

### 6. Mini-Map Test
- [ ] Kleine Map in Ecke sichtbar
- [ ] Avatar-Position als Punkt
- [ ] Symbole als Punkte

### 7. Performance
- [ ] Keine Console Errors (F12 → Console)
- [ ] Keine Lags bei WASD Bewegung
- [ ] 60fps (im Normalfall)

---

## Bei Bug-Fix commits
- [ ] Bug lokal reproduzieren
- [ ] Fix anwenden
- [ ] Bug ist behoben (erneut testen)
- [ ] Keine neuen Bugs eingeführt (kurz alle Tests)

---

## Bei grossen Features
- [ ] Alle Basis-Tests bestanden
- [ ] Edge Cases getestet
- [ ] Auf unterschiedlichen Bildschirmgrößen (Resize)
- [ ] Mobile/Touch getestet (falls relevant)

---

## Bug Report Template (für VIOLIN)
```
Datum: YYYY-MM-DD HH:MM
Browser: Chrome/Firefox/Safari/Edge
Steps to Reproduce:
1. 
2. 
3. 
Erwartet: 
Tatsächlich: 
Screenshot: (falls möglich)
```
