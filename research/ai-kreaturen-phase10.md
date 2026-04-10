## Research: AI/Kreaturen — Phase 10

### Key Principles (aus Web-Research)
1. **State Machine** — PATROL, CHASE, ATTACK, FLEE
2. **Reaktions-Delay** — 0.3s Verzoegerung bevor Angriff
3. **"Last Known Position"** — Feinde merken sich letzte Position des Spielers
4. **Umgebungsbewusstsein** — Raycasts fuer Wände, Klippen
5. **"Believability through imperfection"** — Feinde sollten auch mal stolpern

###Fuer Nemo's Alchemie:
- Symbole sind die "Beute" fuer Kreaturen
- Kreaturen mit Patterns (nach Biome unterschiedlich)
- Einfach: IGNIS-Feinde greifen an, AQUA-Feinde fliehen bei tiefem HP
- Spieler muss Kreaturen "besiegen" um Biome zu erkunden

### Pattern-Ideen:
| Biome | Kreatur | Verhalten |
|-------|---------|-----------|
| IGNIS | Feuer-Wolf | Verfolgt, greift an |
| AQUA | Wasser-Schleim | Flieht, kommt zurueck |
| TERRA | Stein-Golem | Patrouilliert, blockiert Weg |
| AETHER | Geist | Unsichtbar bis nahe, dann Flucht |

### Implementation (einfach):
```
State Machine:
- IDLE: Animiert warten, 2s Pause
- PATROL: Kurze Wege patrouillieren
- CHASE: Spieler verfolgen (mit Verzoegerung)
- ATTACK: Schaden wenn nah
- FLEE: Zurueckziehen wenn HP < 30%
```

### Lessons:
- Nicht zu komplex — State Machine reicht
- Verzoegerungen machen AI "lebendig"
- "Believably dumb" ist besser als "perfect but boring"
