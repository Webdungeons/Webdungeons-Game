# Analyse: Was Web Dungeons: Eclipse noch fehlt

## Kontext der Analyse
Diese Analyse basiert auf dem aktuellen Stand der Codebasis (eine einzige `game.html` + `README.md`).

---

## 1) Executive Summary (kurz)

Das Spiel hat bereits **viel Content und Systeme** (Klassen, Talente, Dungeons, Events, Loot, Crafting, Prestige, Achievements).

Die größten Lücken liegen aktuell in drei Bereichen:

1. **UX/UI-Qualität & Bedienbarkeit** (Lesbarkeit, Informationsdichte, mobile Nutzung, Accessibility, Input-Flow)
2. **Kampf-Tiefe über längere Sessions** (zu wenig situative Entscheidungen pro Runde, wenig Gegnerrollen/Phasenvielfalt)
3. **Langfristige Motivation/Meta** (klarere Midgame-Goals, stärkere Endgame-Schleifen, besseres Pacing)

---

## 2) Stärken (damit klar ist, worauf aufgebaut werden kann)

- Solide Systembreite: Klassen, Skilltree, Crafting, Quests, Prestige, Achievements.
- Mehrere Progressionsachsen (Gear, Talentpunkte, Prestige-Buffs, Meta-Boni).
- Gute Content-Basis für Single-File-Spiel (Areal-/Dungeon-Varianten, Events, Mutatoren).
- Sehr viele vorhandene UI-Komponenten, die man iterativ verbessern kann statt neu zu bauen.

---

## 3) Was konkret fehlt – nach Bereichen

## A) UI/UX: Hier ist der größte Hebel

### A1. Informationsarchitektur im Kampf ist noch zu „text-lastig“
**Problem:** Wichtige Combat-Informationen (Debuffs, Cooldowns, nächster Power-Spike, Gefahr) gehen im Log unter.

**Fehlt:**
- Ein kompakter „Taktik-Block“ über den Kampfbuttons:
  - Erwarteter gegnerischer Schaden (Range)
  - Restliche Effekt-Dauer (z. B. Gift 2 Runden)
  - Nächste Boss-Phase-Schwelle
- Deutliche telegraphische Hinweise bei gegnerischen Spezialangriffen (nicht nur Log-Zeile).

**Wirkung:** Mehr Lesbarkeit, mehr „ich treffe bewusst Entscheidungen“ statt reaktiv klicken.

---

### A2. Action-Buttons sind funktional, aber nicht kontext-intelligent genug
**Problem:** Der Kampf hat fast immer dieselben 5 Buttons (Attacke, Skill, Ult, Trank, Flucht).

**Fehlt:**
- Kontext-Prompts: „Ult jetzt effizient“ / „Skill killt sicher“ / „Trank überheilt >30%, warten?“
- Soft-Autoplay für grinds (optional) mit Regeln („nutze Trank unter 35% HP“).

**Wirkung:** Weniger monotoner Midgame-Grind und bessere Einstiegserfahrung.

---

### A3. Mobile & Responsive ist nur basic
**Problem:** Das Layout nutzt feste Größen/Pane-Logik, mobile ist nur begrenzt angepasst.

**Fehlt:**
- Vollwertiger Mobile-Kampflayout-Modus (große Primärbuttons, sticky Kerninfos)
- Optionaler „Compact UI“-Schalter (kleinere Karten/Logs, weniger Deko)

**Wirkung:** Spielbar auf Handy ohne „zu klein/zu voll“-Gefühl.

---

### A4. Accessibility fehlt fast komplett
**Problem:** Stark visuell/hoverbasiert, wenig semantische Bedienpfade.

**Fehlt:**
- Tastatur-Navigation (Hotkeys 1–5 für Kampfaktionen)
- Fokus-Ringe, ARIA-Labels, klare Kontraste für Statuszustände
- Reduzierte Effekte (Motion Toggle)

**Wirkung:** Größere Zielgruppe, weniger Friktion.

---

## B) Kampfsystem: Du hast recht – noch teilweise zu langweilig

### B1. Kernrotation wiederholt sich zu früh
**Problem:** Trotz Effekten ist der Entscheidungsraum pro Runde relativ klein.

**Fehlt:**
- Klassen-spezifische Subsysteme mit echter Entscheidung:
  - Ritter: Guard-Stance vs. Counter-Stance
  - Magier: Elementwahl (Burst vs. Control)
  - Schurke: Finishers abhängig von Combo-Level
- Leichte Cooldown-/Ladungsmechaniken bei Skills (statt nur MP-Kosten)

**Wirkung:** Mehr Build-Identität und weniger „immer dieselbe Reihenfolge“.

---

### B2. Gegner-KI/Archetypen sind noch zu flach
**Problem:** Gegnerfähigkeiten sind vorhanden, aber die Verhaltensmuster sind kurzzyklisch.

**Fehlt:**
- Klare Archetypen mit lesbaren Kampfplänen:
  - Bruiser (langsam, schwer)
  - Controller (Stun/Weak Fokus)
  - Sustain (heal/reflect)
- Multi-Turn-Telegraphing (z. B. „lädt Finisher in 1 Runde“) als Counterplay-Fenster.

**Wirkung:** Kampf wird taktischer statt zufallslastiger.

---

### B3. Boss-Design hat Potenzial, aber noch zu wenig Varianz
**Problem:** Boss-Phase 2 ist gut, aber oft noch "mehr Stats" statt neue Entscheidungslage.

**Fehlt:**
- Boss-spezifische Minimechaniken je Dungeon (z. B. Adds, Schildfenster, Interrupt-Fenster)
- 2–3 einzigartige Boss-Patterns pro Dungeon statt primär Stat-Skalierung

**Wirkung:** Bosskämpfe werden merkbar unterschiedlich und erinnerbar.

---

## C) Progression & Economy

### C1. Midgame-Pacing braucht „geführte Meilensteine“
**Problem:** Viele Systeme sind da, aber der Spieler bekommt zu wenig strukturierte Zwischenziele.

**Fehlt:**
- Chapter-Missions (z. B. „Erreiche Floor X“, „Baue Build Y“) mit starken einmaligen Rewards
- Sichtbare „Empfohlener Power-Score“-Hinweise vor Dungeons

**Wirkung:** Weniger Lost-Feeling, klarere Richtung.

---

### C2. Endgame-Motivation kann deutlich stärker werden
**Problem:** Endlos-Dungeon + Prestige existieren, aber das Endgame-Ziel ist noch eher offen.

**Fehlt:**
- Saisonale/zyklische Challenges (weekly modifiers)
- Build-definierende set-ähnliche Item-Boni
- Späte Meta-Entscheidungen (Prestige-Pfade statt nur lineare Buff-Upgrades)

**Wirkung:** Mehr langfristiger Wiederspielwert.

---

### C3. Economy braucht zusätzliche Gold-/Shard-Sinks
**Problem:** Auf längere Sicht droht Overflow oder eindimensionale Ausgabenstruktur.

**Fehlt:**
- Gold-Shards-Konvertierung mit schlechten Raten (stabilisiert Overflow)
- Teure QoL-Upgrades (z. B. Truhen-Bulk-Öffnen, Affix-Reroll, Storage-Filter)
- Risikoökonomie (z. B. „blutige Schmiede“ mit Failchance und Jackpot)

**Wirkung:** Mehr strategische Ressourcenentscheidungen.

---

## D) Content/Lore/Questing

### D1. Quest-System ist solide, aber noch zu generisch
**Fehlt:**
- Kettenquests mit Story-Hooks je Gebiet
- Klassenquests (pro Klasse 2–3 exklusive Aufgaben + Belohnung)
- Entscheidungsquests (Belohnung A vs. B, dauerhaft)

**Wirkung:** Bessere Bindung, weniger „rein mathematische Aufgaben“.

---

### D2. Weltgefühl kann stärker werden
**Fehlt:**
- Kurze Event-Illustrationen/Encounter-Texte mit Konsequenzen
- Mehr Lore-Freischaltungen außerhalb von Bossen

**Wirkung:** Höhere Immersion.

---

## E) Technik & Produktqualität

### E1. Wartbarkeit ist kritisch (Monolith)
**Problem:** Alles in einer großen HTML-Datei bremst Tempo und Stabilität bei neuen Features.

**Fehlt:**
- Modularisierung (z. B. `combat.js`, `ui.js`, `economy.js`, `save.js`)
- Kleine interne API-Schicht für State-Änderungen

**Wirkung:** Schnellere Iteration, weniger Regressionen.

---

### E2. Testbarkeit fehlt
**Fehlt:**
- Deterministische Simulation (Seeded RNG) für Balancing-Tests
- Mini-Testset für Kernregeln (damage, loot, save migration)

**Wirkung:** Balancing wird messbar statt „Gefühl“.

---

### E3. UX-Basics über `prompt/confirm` sind altbacken
**Fehlt:**
- Ingame-Modals für Nameingabe, Save-Slots, kritische Bestätigungen
- Save-Slot-Metadaten mit „Playtime / Last run summary“

**Wirkung:** Professioneller Flow, weniger Brüche.

---

## 4) Priorisierte Umsetzungs-Roadmap

## Phase 1 (1–2 Wochen) – „Sofort spürbar“
1. Kampf-UI-Verbesserung: Taktik-Infos + bessere Effektanzeige
2. Keyboard-Hotkeys + Accessibility-Basics
3. Ingame-Modals statt `prompt/confirm`
4. Erste Combat-Varianz: 1 neue Klassenmechanik + 1 neue Bossmechanik pro Dungeon

**Ergebnis:** Spürbar weniger langweilige Kämpfe, bessere Bedienung.

---

## Phase 2 (2–4 Wochen) – „Tiefe und Retention“
1. Gegner-Archetypen + Telegraphing-System
2. Midgame-Chapter-Missionen + empfohlener Power-Score
3. Economy-Sinks + Affix-Reroll
4. Questketten und Klassenquests

**Ergebnis:** Besseres Pacing, mehr Build- und Zielgefühl.

---

## Phase 3 (4+ Wochen) – „Produktreife“
1. Code-Modularisierung + Basistests
2. Endgame-Saisons/Challenges
3. Erweiterte Meta-Progression (Prestige-Pfade)

**Ergebnis:** Langfristig wartbar + deutlich höhere Wiederspielbarkeit.

---

## 5) Konkrete Antwort auf deine Ansätze

Du liegst mit beiden Punkten richtig:

1. **"Game UI ist schlecht"** → präziser: Nicht „schlecht“, aber **überladen, zu wenig priorisiert und zu wenig führend** im Kampf. Das kostet Entscheidungsqualität.
2. **"Kampf ist teilweise langweilig"** → präziser: Die Basis ist gut, aber **der Entscheidungsraum pro Runde ist zu klein** und Boss-/Gegnerverhalten variiert noch zu wenig in Mustern.

Wenn du nur **eine** Sache zuerst verbessern willst:
> **Kampf-UX + Kampf-Varianz zusammen** angehen (nicht getrennt). Erst dann fühlt sich das Spiel sofort „wie ein neues Spiel“ an.

