# Nemo's Alchemie — Retro-Analyse

## Was Michi bemängelt hat
> "der spieler hat keinen skin, die welt generiert nicht weiter, neue rezepte passiert nicht wirklich was, keine entstehung eines neuen elements"

## Problem 1: Kein Player-Skin
**Status:** Avatar ist nur ein orangefarbener Kreis
- Kein Charakter-Design
- Keine Animation (nur Glow bei Bewegung)
- Keine Richtung-Animation

**Lösung:** 
- Avatar als einfache Figur (Körper + Kopf)
- Richtung zeigt wo er hin geht
- Animation: leichtes "atmen" im Idle

## Problem 2: Welt generiert nicht weiter
**Status:** 2000x2000是真的 aber leer — nur 13 fixe Symbole
- Keine prozedurale Generierung
- Keine Biomes
- Keine Geheimnisse
- Welt fühlt sich statisch an

**Lösung:**
- prozedurale "Zonen" mit Symbolen
- Symbole spawnen in der Welt basierend auf Level/Entdeckungen
- Geheimnisse: versteckte Bereiche

## Problem 3: Rezepte bringen nichts
**Status:** Code funktioniert aber das ERGEBNIS erscheint nicht in der Welt
- Recipe wird in `discoveredRecipes` gespeichert ✓
- XP gegeben ✓
- ABER: Das neue Element taucht NIRGENDS auf
- Kein visueller "Schöpfungs"-Moment

**Lösung:**
- Wenn Recipe entdeckt → neues Symbol in der Welt spawnen
- Particle-Effekt bei Entdeckung
- Das neue Element ist JETZT in der Welt präsent

## Problem 4: Keine echte "Entstehung"
**Status:** Keine Transformation, kein "Geburts"-Moment
- Elemente werden nicht geboren
- Keine Animation wenn etwas NEUES entsteht
- Kein visueller Impact

**Lösung:**
- Particle-Burst bei Recipe-Entdeckung
- Neues Symbol spawnt mit Animation
- "Schöpfungs"-Feedback

## Geplante Improvements (Phase 3)

### 1. Player Visual Upgrade
```
- Avatar: Körper (Rechteck) + Kopf (Kreis)
- Richtung: Avatar dreht sich in Bewegungsrichtung
- Animation: leichtes Pulsieren im Idle
- Farbe basierend auf Level (Gradients)
```

### 2. Recipe → Neues Symbol spawnt in Welt
```
- Wenn Recipe entdeckt → neues Symbol spawnt
- Position: Random im Umkreis um Player
- Animation: Fade-in + Particles
- Farbe: Result-Element-Farbe
```

### 3. Progressive World
```
- Level 1-5: 13 Symbole (jetzt)
- Level 6-10: +5 neue pro Level
- Jedes neue Element fügt was zur Welt hinzu
- Biomes: Feuer-Zone, Wasser-Zone, etc.
```

### 4. Visual Feedback
```
- Particle-Burst bei Combination
- Screen-Flash bei neuer Entdeckung
- Sound-Effekte (optional)
```

## Tech-Details

### Neues Symbol Spawn System
```javascript
function spawnResultSymbol(recipe) {
  const resultSymbol = SYMBOLS.find(s => s.id === recipe.result);
  if (!resultSymbol) return;
  
  // Neues Symbol spawnen
  const angle = Math.random() * Math.PI * 2;
  const dist = 200 + Math.random() * 300;
  const nx = state.avatar.x + Math.cos(angle) * dist;
  const ny = state.avatar.y + Math.sin(angle) * dist;
  
  // Clamp to world
  const x = Math.max(100, Math.min(state.world.width - 100, nx));
  const y = Math.max(100, Math.min(state.world.height - 100, ny));
  
  // Spawn animation + particles
  createSpawnEffect(x, y, resultSymbol.color);
  
  // Symbol zur Welt hinzufügen
  resultSymbol.x = x;
  resultSymbol.y = y;
  resultSymbol.spawned = true;
  resultSymbol.spawnTime = Date.now();
}
```

### Particle System (einfach)
```javascript
const particles = [];

function createSpawnEffect(x, y, color) {
  for (let i = 0; i < 20; i++) {
    particles.push({
      x, y,
      vx: (Math.random() - 0.5) * 10,
      vy: (Math.random() - 0.5) * 10,
      life: 1.0,
      color,
      size: 3 + Math.random() * 5
    });
  }
}

function updateParticles() {
  particles.forEach(p => {
    p.x += p.vx;
    p.y += p.vy;
    p.life -= 0.02;
    p.vy += 0.1; // gravity
  });
  // Remove dead particles
}

function drawParticles() {
  particles.forEach(p => {
    ctx.globalAlpha = p.life;
    ctx.fillStyle = p.color;
    ctx.beginPath();
    ctx.arc(p.x - camera.x, p.y - camera.y, p.size, 0, Math.PI * 2);
    ctx.fill();
  });
  ctx.globalAlpha = 1;
}
```

## Nächste Schritte (Phase 3)
1. [ ] Player-Skin (Figur statt Kreis)
2. [ ] Recipe → Symbol spawnt in Welt
3. [ ] Particle-Effekte bei Entdeckung
4. [ ] Spawn-Animation
5. [ ] World Expansion (mehr Symbole pro Level)

---

_Zuletzt aktualisiert: 2026-04-07 23:00_
