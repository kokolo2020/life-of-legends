# 🌳 LIFE OF LEGENDS — Game Design Document (GDD)
**Version:** 1.0  
**Platform:** Roblox  
**Type:** Multiplayer Social Action RPG  
**Status:** Pre-Production / Design Phase  

---

## 📋 TABLE OF CONTENTS
1. [Game Overview](#overview)
2. [Top 3 Games Inspiration](#inspiration)
3. [World Map & Spawn Area](#world)
4. [The Crystal Dome & Towers](#dome)
5. [Player Roles](#roles)
6. [Game Modes](#modes)
7. [Pet System](#pets)
8. [Social System](#social)
9. [Group Quests](#quests)
10. [Rewards & XP](#rewards)
11. [Monetization](#monetization)
12. [Referral System](#referral)
13. [Anti-Bot System](#antibot)
14. [Technical Notes](#technical)

---

## 1. GAME OVERVIEW <a name="overview"></a>

**Concept:**  
A multiplayer social RPG combining the top 3 Roblox games into one world. Players spawn at the Tree of Life, raise pets, farm crops, collect Brainrot characters, steal from rivals, fight with Devil Fruit powers, run dungeons, and compete in a 10-minute Royal Rumble — all in one game.

**Core Loop:**
```
Spawn at Tree of Life
  → Choose role (Tank / Healer / DPS)
  → Get starter pet from Elder Mira (Quest 1)
  → Farm, fight, collect, socialize
  → Play Royal Rumble (10 min battle royale)
  → Top 5 enter Crown Run (puzzle + obstacle race)
  → OR queue for Dungeon Run (5-player co-op, 4 bosses)
  → Earn XP + Leaves + Chests
  → Level up → unlock floors → subscribe for pod home
  → Repeat daily
```

**Server Size:** 50 players (expandable to 100)  
**Target Age:** 10+  
**Version 1:** Free to play — all gameplay free, homes subscription only

---

## 2. TOP 3 GAMES INSPIRATION <a name="inspiration"></a>

### 🐣 Adopt Me (78B+ visits)
| Feature | Implementation |
|---------|---------------|
| Pet aging stages | Egg → Newborn → Junior → Pre-Teen → Teen → Full Grown |
| Pet accessories | Hats, scarves, wings, auras — cosmetic only |
| Trading marketplace | Trade pets/crops/items at market stall |
| Vehicles | Cars, bikes, scooters in City District |
| Homes | Pod towers — subscription only |

### 🧠 Steal a Brainrot (24M peak CCU)
| Feature | Implementation |
|---------|---------------|
| Brainrot collectibles | Italian-themed characters on conveyor belt |
| Stealing mechanic | Steal carried items from other players |
| Base defense | Shield button + purchasable traps |
| Conveyor belt | New Brainrot every 30s in City District |
| Rebirth system | Reset level at 100 for permanent perks |

### ⚔️ Blox Fruits (58B+ visits)
| Feature | Implementation |
|---------|---------------|
| Devil Fruits | 6 fruits hidden per match, first-come power-ups |
| Fruit mastery | Each fruit levels 1–100, unlocks new abilities |
| Multiple seas | First Sea (1–30), Second Sea (31–70), Third Sea (71–100) |
| Raids | Server-wide boss every 45 min — all players fight |
| Sword mastery | Melee weapons level 1–100 alongside fruits |
| Bounty system | Kill/steal to earn bounty, top 5 on board weekly |

---

## 3. WORLD MAP & SPAWN AREA <a name="world"></a>

### Layout (Bird's Eye)
```
                    🌊 COMBAT SEAS (Blox Fruits zone)
                         ↑
          🏙️🏙️🏙️              🏙️🏙️🏙️
       🏙️                              🏙️
      🏙️       ╔════════════════╗       🏙️
🏘️ ← 🏙️       ║   🔮 CRYSTAL   ║       🏙️ → 🌱
CITY  🏙️       ║   DOME + 🌳   ║       🏙️  GARDEN
      🏙️       ╚════════════════╝       🏙️
       🏙️                              🏙️
          🏙️🏙️🏙️              🏙️🏙️🏙️
                         ↓
                    ☠️ DUNGEON ENTRANCE
```

**Map diameter:** ~700 studs  
**Total map size:** Manageable, streaming-enabled for performance

### Tree of Life (Hub)
- Height: 150 studs — visible from entire map
- Trunk: 30 studs wide, climbable bark
- Roots: 8 giant roots glow and change color by game phase
- Particles: Golden leaves drift upward constantly
- Fountain at base: Full heal, respawn protection zone

### Game Phase — Tree Color
| Phase | Root Color | Sound |
|-------|-----------|-------|
| Lobby/Waiting | Soft gold | Wind chimes |
| Prep Phase (0–2 min) | Warm orange | Building drums |
| Combat Phase (2–7 min) | Pulsing red | Battle drums |
| Zone Collapse (7–9 min) | Flickering red | Rumbling |
| Last Stand (9–10 min) | White flash | Epic orchestral |
| Dungeon Active | Deep purple | Eerie ambience |
| Match Won | Rainbow | Victory fanfare |

### Zones
| Zone | Inspired By | What's There |
|------|-------------|--------------|
| 🌱 Garden District (East) | Grow a Garden | Crops, farming, market |
| ⚔️ Combat Seas (North) | Blox Fruits | Fruits, PvP, bosses |
| 🏘️ City District (West) | Brookhaven RP | Cars, houses, brainrot conveyor |
| ☠️ Dungeon (South/Down) | Original | 4 bosses, co-op |

---

## 4. CRYSTAL DOME & POD TOWERS <a name="dome"></a>

### The Crystal Dome
- 40 stud diameter glass dome surrounding the Tree trunk
- 4 archways (N/S/E/W) — each faces a zone
- Inside: Teleport pads, fountain, Bounty Board, Elder Mira NPC, benches
- Teleport pad per player: GREEN = online, GREY = offline
- Step on own pad → teleport home
- Step on other's pad → send visit request

### Pod Tower System
- 12 towers arranged in a circle around the dome
- Each tower: 10 floors × 2 pods per floor = 20 pods/tower
- 12 towers × 20 pods = **240 pods total** (covers 50-player servers easily)
- All towers face inward toward the Tree of Life

### Tower Floor Assignment by Level
| Floor | Level Range | Title |
|-------|-------------|-------|
| 1 | 1–10 | 🌱 Seedling |
| 2 | 11–25 | 🌿 Sprout |
| 3–4 | 26–50 | ⚔️ Fighter |
| 5–6 | 51–70 | 🔥 Warlord |
| 7–8 | 71–90 | 🌟 Legend |
| 9 | 91–99 | 👑 Champion |
| 10 | Prestige 1+ | 🌟 PENTHOUSE |

### Pod Features
- 16×20×8 studs per pod
- Glass front wall facing the Tree
- Balcony garden (replaces ground garden — 6 planter slots)
- Inside: bed, storage chest, pet corner, campfire
- **HOME IS SUBSCRIPTION ONLY — free players spawn at dome**

### Subscription Tiers
| Pass | Price | Key Perks |
|------|-------|-----------|
| 🌿 Sprout Pass | 80 R$/mo | Floor 1–3 pod, 4 garden slots, chest (20), teleport pad |
| 🔥 Legend Pass | 200 R$/mo | Floor 1–8 pod, 8 slots, 1.25x Leaves, gold name |
| 👑 Guardian Pass | 400 R$/mo | All floors + penthouse, 12 slots, auto-waterer, crown tag |

**Free players:** Full gameplay, no home, spawn at dome fountain.

---

## 5. PLAYER ROLES <a name="roles"></a>

Chosen at game start. Affects dungeon only — all roles work in open world.

### 🛡️ Tank
- HP: 350 | Damage: Low
- **Q** Iron Guard — 50% damage reduction 4s (15s cd)
- **E** Taunt — force boss aggro 8s (10s cd)
- **R** Shield Slam — stun 2s + 40 dmg (20s cd)
- **F** Fortress — AOE shield all nearby allies 3s (45s cd)
- Passive: Every 5 hits taken → reflect 10 damage

### 💚 Healer
- HP: 180 | Damage: Very Low
- **Q** Heal Beam — heal 1 target 60 HP (8s cd)
- **E** Life Bloom — AOE heal 30 HP nearby (20s cd)
- **R** Revive — revive downed player at 50% HP (60s cd)
- **F** Holy Barrier — shield all 5 players for 5s (90s cd)
- Passive: 2 HP/sec regen near allies

### ⚔️ DPS — 3 Sub-Classes

**🗡️ Blade Warrior (Melee)**
- HP: 220 | Q: Combo Slash | E: Dash Strike | R: Spin Blade | F: EXECUTE (<20% HP = 200 dmg)
- Passive: Every 3rd hit is a critical (1.5x)

**🏹 Fruit Sniper (Ranged)**
- HP: 200 | Q: Fruit Burst (charged) | E: Scatter Shot | R: Devil Eye (mark target) | F: SNIPER MODE (300 dmg)
- Passive: Headshots deal 2x damage

**🔥 Fruit Mage (Magic)**
- HP: 190 | Q: Magma Wave | E: Ice Prison | R: Wind Blast | F: FRUIT STORM
- Passive: Ice → Fire combo = 2x damage

---

## 6. GAME MODES <a name="modes"></a>

### ⚔️ Royal Rumble (10 Minutes)
```
0:00–2:00  PREP PHASE    → No combat, grab fruits, farm, loot city
2:00–7:00  OPEN WAR      → PvP active, every kill announced globally
7:00–9:00  ZONE COLLAPSE → Zones flood/burn, all pushed to Tree
9:00–10:00 LAST STAND    → Everyone fights at Tree roots
End:       Top 5 survivors → enter Crown Run
```

**Zone bonuses during Rumble:**
- Garden: Crops = HP potions during combat
- Combat Seas: 6 Devil Fruits hidden, first-come power-ups
- City: Loot houses for weapons, steal cars to ram players, gas station traps

### 👑 Crown Run (5 Stages — Top 5 Survivors)
Fastest to complete all stages wins the Crown.

| Stage | Theme | Puzzle | Obstacle |
|-------|-------|--------|----------|
| 1 | 🌱 Garden Maze | Pull 3 levers in correct order | Shrinking maze paths, vine traps |
| 2 | ⚔️ Fruit Power Trial | Use random fruit on 3 rooms | Rotating blades, crystals, platforms |
| 3 | 🏙️ City Rooftop Rush | Step on plates in sequence | Moving cranes, rooftop gaps |
| 4 | 🌳 Tree of Life Ascent | 3-question quiz about that match | Rotating platforms, fire jets, disappearing tiles |

Winner grabs the glowing Crown at the top → fireworks → Champion announced globally.

### ⚔️ Dungeon Run (5 Players, 30 Minutes, 4 Bosses)

**Timer breakdown:**
```
0:00–5:00   Path to Boss 1 (trash mobs, learn mechanics)
5:00–10:00  Boss 1 — Vine Colossus (⭐⭐)
10:00–14:00 Checkpoint + path to Boss 2
14:00–18:00 Boss 2 — Sea Tyrant (⭐⭐⭐)
18:00–21:00 Path to Boss 3 (darkness, harder mobs)
21:00–25:00 Boss 3 — City Phantom (⭐⭐⭐⭐)
25:00–27:00 Final path — roots crumbling
27:00–30:00 Boss 4 — Corrupted Guardian (⭐⭐⭐⭐⭐, 3 phases)
```

**Boss Mechanics Summary:**
- **Vine Colossus:** Root traps, vine minions, destroy 4 weak-point roots
- **Sea Tyrant:** Tidal waves, flooding chamber, Mega Wave requires Tank+Healer combo
- **City Phantom:** Invisibility, possession (controls player), solve lantern puzzle to reveal
- **Corrupted Guardian:** 3 phases, bark armor (break with Ice+Fire combo), Soul Harvest 1-hit KO, coordinated DPS nuke to kill

**Loot:** Personal loot (no stealing), role-weighted drops, rarity increases per boss (Boss 4: 40% Legendary, 18% Mythic, 2% Guardian)

### 🌍 Open World (Always On)
- Free roam all 3 zones anytime
- Raids every 45 minutes (server-wide boss)
- Brainrot conveyor in City (buy or steal)
- Farming, trading, socializing, pet raising

---

## 7. PET SYSTEM <a name="pets"></a>

### Quest 1 — "Find Your Companion"
- NPC: Elder Mira (mossy rock, 15 studs east of Tree)
- 3 starter eggs on stone table after role selection
- Pick egg → pet hatches with animation → Quest Complete
- Reward: Common pet + 100 XP + 50 Leaves

| Egg | Pet | Passive Ability |
|-----|-----|----------------|
| 🥚 Forest Egg | 🐢 Mossy Tortoise | +15 max HP |
| 🥚 Storm Egg | 🦅 Tide Hawk | +10% move speed |
| 🥚 Shadow Egg | 🦊 Night Fox | Nearby enemies on minimap |

### Pet Aging Stages (Adopt Me Style)
```
🥚 Egg       → 25% ability | Just hatched
🐣 Newborn   → 25% ability | Tiny cute form
👶 Junior    → 50% ability | Growing
🧒 Pre-Teen  → 75% ability | Almost there
🧑 Teen      → 100% ability | Full size
🧔 Full Grown → 125% ability | Glowing upgraded look
```
Age up by: equipping and playing, feeding (Leaves), pet tasks.

### Pet Rarities
| Rarity | Egg Chance | Example |
|--------|-----------|---------|
| ⬜ Common | 60% | Baby Chick — radar pings nearby enemies |
| 🟦 Rare | 25% | Forest Fox — sniffs hidden crops |
| 🟣 Epic | 12% | Mini Dragon — shoots fireballs |
| 🟡 Legendary | 2.5% | Spirit Moth — revive once per match |
| 🔴 Mythic | 0.5% | Cosmic Orb — reveals all fruit locations |
| 🌳 Guardian | World drop | Tree Spirit — heals nearby allies, gold aura |

### Pet Leveling & Evolution
- Pet Level 1–30 (XP from matches, feeding)
- Level 5: cd reduced 20% | Level 10: stronger ability | Level 20: EVOLVES | Level 30: MAX + golden glow
- Evolution examples: Baby Chick → Thunder Parrot | Forest Fox → Shadow Wolf

### Pet Fusion
- Fuse 2 pets of same rarity at Level 30
- Combines both abilities, hybrid appearance, rarity upgrades 1 tier

### Pet Accessories (Cosmetics)
- Hats, scarves, backpacks, wings, auras
- Earned via Leaves, Crown Gems, achievements

---

## 8. SOCIAL SYSTEM <a name="social"></a>

### Interactions That Earn XP (Daily Capped)
| Action | XP | Leaves | Daily Limit |
|--------|-----|--------|-------------|
| 👋 Wave at player | +10 | +5 | 20 |
| 🤝 Shake hands (both agree) | +25 | +10 | 10 |
| 💬 Send chat message | +5 | — | 30 |
| 🎁 Gift crop to player | +30 | +15 | 5 |
| 🐾 Pet another player's pet | +15 | +5 | 10 |
| 🏠 Visit subscriber's home | +20 | +10 | 5 |
| 🌱 Water someone's garden | +25 | +15 | 5 |
| 🔗 Trade items with player | +35 | +20 | 3 |

**Daily social XP cap:** Free=500, Sprout=750, Legend=1000, Guardian=1500

### Trading Marketplace (Adopt Me Style)
- Trade window: offer pets, crops, items, accessories
- Trade board: post listings + browse others
- Anti-scam: full summary screen + "Are you sure?" + 2min cooldown
- New accounts under 7 days: trade locked

### Stealing Mechanic (Steal a Brainrot Style)
**Can steal:** Brainrot characters being carried, crops just harvested, fruits just picked up  
**Cannot steal:** Stored items, equipped pets, currency, anything inside the dome/towers

**How to steal:**
1. Get within 5 studs of target
2. Press [STEAL] — 3s animation, you're vulnerable
3. Success → you have it, they're alerted, you're slowed 50% for 8s
4. Fail (shield active) → nothing, 30s cooldown

**Thief status:** Icon above head for 60s — anyone can attack you.

### Defense System
- Basic Shield: blocks 1 steal, 60s cd (free)
- Tower Shield: blocks 3 steals, 2min cd (500 Leaves)
- Guardian Shield: auto-activates (Guardian Pass)
- Traps: Vine (slow 80%), Bomb Flower (stun 3s), Alert Bell (notify)

### Vehicles (Adopt Me Style)
- 🛴 Scooter: free | 🚗 Car: 200 Leaves | 🏎️ Sports Car: 500L | 🚁 Helicopter: Legendary achievement
- Drive for XP, carry passengers, ram enemies in Rumble

---

## 9. GROUP QUESTS <a name="quests"></a>

- 2–5 players, started at Quest Board near dome
- ALL members get FULL reward (not split)
- Refresh every 2 hours
- **All easy on purpose — social, not grind**

### Sample Quests
| Quest | Task | Time | Reward |
|-------|------|------|--------|
| 🌱 Community Garden | Each member harvest 5 crops | 5 min | 200 XP + 150 Leaves |
| 🌊 Water Your Neighbour | Water 1 crop in a member's garden | 2 min | 150 XP + 100 Leaves |
| 🐾 Pet Parade | Walk together 30s with pets out | 1 min | 150 XP + Pet XP boost |
| 👋 Welcome Wagon | Wave at a new player (under Level 5) | 2 min | 175 XP + Mentor badge |
| 🌳 Group Photo | Stand at Tree together 10 seconds | 30 sec | 100 XP + 75 Leaves |
| 👁️ Witness the Battle | Watch a Royal Rumble in spectator zone | 5 min | 100 XP + 50 Leaves |
| 🏙️ Tower Tour | Visit 3 different towers as a group | 5 min | 200 XP + 150 Leaves |
| 💀 Legendary Run | Complete 1 dungeon together | 30 min | 1000 XP + Gold Chest + Rare Egg |

---

## 10. REWARDS & XP <a name="rewards"></a>

### Two Currencies
| Currency | Earned By | Spent On |
|----------|-----------|---------|
| 🌿 Leaves | Playing, quests, farming, kills | Cosmetics, pets, gear, upgrades |
| 👑 Crown Gems | Winning Crown Run, Guardian Pass | Exclusive Mythic items only |

### XP Sources
```
Kill in Rumble          → 40 XP      Win Rumble         → 250 XP
Dungeon boss (shared)   → 200 XP     Win Crown Run      → 400 XP
Stage cleared           → 80 XP      Harvest rare crop  → 40 XP
Daily quest             → 100–300 XP Daily login        → 100 XP
Pet levels up           → 50 XP      Social interaction → 5–35 XP
```

### Level Table
| Range | Title | XP/Level |
|-------|-------|----------|
| 1–10 | 🌱 Seedling | 500 |
| 11–25 | 🌿 Wanderer | 1,000 |
| 26–50 | ⚔️ Fighter | 2,000 |
| 51–70 | 🔥 Warlord | 4,000 |
| 71–90 | 🌟 Legend | 8,000 |
| 91–99 | 👑 Champion | 15,000 |
| 100 | 🌳 Tree Guardian | MAX — PRESTIGE unlocks |

### Level Unlock Gates (Free)
```
Level 5   → 2nd pet slot          Level 25  → 3rd pet slot
Level 10  → Dungeon mode          Level 30  → Pet fusion
Level 15  → Pet evolution         Level 50  → Fruit Sniper unlocked
Level 20  → Crown Run leaderboard Level 100 → PRESTIGE
```

### Daily Login Streak
```
Day 1: 100 Leaves | Day 2: 150L + 50 XP | Day 3: 200L + Common Egg
Day 4: 300L + 200 XP | Day 5: Rare Egg + 500L | Day 6: 400L + 300 XP
Day 7: EPIC EGG + 1,000L + 500 XP ← weekly payoff
```

### Match Reward Chests
| Placement | Chest | Guaranteed |
|-----------|-------|-----------|
| Bottom 50% | 📦 Wood | 1 item + small Leaves |
| Top 50% | 🥈 Silver | 2 items + medium Leaves |
| Top 3 | 🥇 Gold | 3 items + large Leaves + XP boost |
| Crown Run Win | 💎 Diamond | 4 items + Crown Gems + pet egg |
| 3 wins in a row | 🌳 Tree | Legendary guaranteed + fusion token |

### Prestige System
At Level 100 → Prestige (reset to Level 1, keep all pets/cosmetics/home)  
Each Prestige adds ⭐ badge + 2x XP boost for that run. Max Prestige 5.

### Rebirth System (Steal a Brainrot Style)
At Level 100 → REBIRTH option (different from Prestige — focused on permanent stat boosts)
```
Rebirth 1 → +10% Leaves earned permanently
Rebirth 2 → Exclusive pet skin
Rebirth 3 → Brainrot Supremo character unlock
Rebirth 4 → 2x crop grow speed permanently
Rebirth 5 → MYTHIC REBIRTH STATUS — golden everything
```

### Fruit & Sword Mastery (Blox Fruits Style)
- Each fruit/sword levels 1–100 mastery separately
- Mastery earned from combat use
- Mastery 25: 2nd ability | Mastery 50: +50% damage | Mastery 75: 3rd ability | Mastery 100: AWAKENED FORM

### Raids (Blox Fruits Style)
Server-wide event every 45 minutes — all players fight together
```
🌊 Tide Kraken   → invades Combat Seas (Level 20+ recommended)
🌿 Vine Titan    → invades Garden District (any level)
🏙️ City Phantom  → invades City District (Level 40+)
🌳 Corrupted Tree → invades the dome itself (Level 60+)
```
Rewards: Leaves scaled to damage, rare fruit drop, exclusive cosmetics.

### Bounty System (Blox Fruits Style)
- Earn bounty from kills (+100), stealing (+150), Rumble win (+500)
- Top 5 on Bounty Board in dome
- Kill high-bounty = steal 20% of their bounty
- Weekly reset: Top 1 gets "Most Wanted" title + 1,000 Leaves

### Brainrot Collectibles (Steal a Brainrot Style)
- Conveyor in City District — new character every 30s
- Buy with Leaves OR steal from other players who bought
- Display in pod home trophy wall
- Rares give passive bonuses
```
🐊 Crocodilo Guardiano  → Common   100 Leaves
🦁 Leone della Vita     → Rare     300 Leaves
🌊 Squalo del Mare      → Epic     800 Leaves
🔥 Drago di Fuoco       → Legendary 2,000 Leaves
🌳 Albero Eterno        → Mythic   Crown Gems only
🧠 Il Brainrot Supremo  → Guardian World drop
```

### Multiple Seas (Blox Fruits Style)
```
First Sea  (Level 1–30)  → Starter area, basic fruits, easy enemies
Second Sea (Level 31–70) → Unlock via "Sea Trial" quest, stronger content
Third Sea  (Level 71–100)→ Rarest fruits/Brainrots, hardest enemies, prestige area
```

---

## 11. MONETIZATION <a name="monetization"></a>

### V1 — Free to Play (Build Now)
Everything gameplay-related is free. Homes are the only paid feature.

### Subscription Passes (Monthly)
| Pass | Price | Main Perks |
|------|-------|-----------|
| 🌿 Sprout | 80 R$/mo | Pod (Floor 1–3), garden, chest, teleport pad |
| 🔥 Legend | 200 R$/mo | Pod (Floor 1–8), 1.25x Leaves, gold name glow |
| 👑 Guardian | 400 R$/mo | All floors + penthouse, auto-waterer, crown tag |

### One-Time Gamepasses
```
🌟 VIP Pass (500 R$)     → [VIP] tag, 1.25x Leaves, VIP lounge, early access
🌳 Guardian Pass (1000 R$) → 1.5x Leaves, guardian frame, dedicated server option
```

### Robux Shop (Cosmetics Only — Never Pay to Win)
```
Pet Skins        → 80 R$ each
Trail Effects    → 60 R$ each
Emotes           → 50 R$ each
Title Frames     → 40–75 R$
Announcer Voices → 150 R$ per pack
Battle Pass      → 400 R$/month (3x quest slots, 2x Leaves from quests)
Premium Eggs     → Cosmetic pet skin variants only (100–600 R$)
```

### Conversion Triggers (Built Into Game)
```
Pet "wants to rest" → "Subscribe to give them a home"
Inventory full      → "Subscribe for a storage chest"
Friend has penthouse → Social pressure, aspirational
Win Rumble          → "Subscribers get a trophy wall for this"
```

---

## 12. REFERRAL SYSTEM <a name="referral"></a>

### How It Works
1. Player gets unique code (e.g. HIBROS_X7K2) in Profile tab
2. Share code via [COPY] or [SHARE] button (copies social-ready text)
3. New player enters code on first-join welcome screen
4. Both rewarded instantly

### Rewards
**New player (joining with code):**
- 🥚 1x Rare Pet Egg
- 🌿 500 Leaves
- ⬆️ 200 XP
- 🏷️ "Referred Legend" badge

**Referrer (per successful referral):**
- 🌿 300 Leaves + ⬆️ 150 XP + 1x Silver Chest roll

**Referrer Milestones:**
```
3  referrals → Rare Pet Egg
5  referrals → Epic Pet Egg + "Recruiter" title
10 referrals → Legendary Pet Egg + golden name
25 referrals → Mythic Pet Egg + "Legend Recruiter" title
50 referrals → PIONEER cosmetic (exclusive forever) — cap
```

### Anti-Abuse Rules
1. New account must be 24hrs+ old
2. New player must play 30+ minutes before reward triggers
3. 1 referral code per account ever
4. Referrer must have 2+ hours playtime
5. Max 50 referral rewards per player
6. Same IP limited to 3 referrals (family protection)

---

## 13. ANTI-BOT SYSTEM <a name="antibot"></a>

### 6 Layers of Protection

**Layer 1 — Roblox Built-In (Free)**
- CAPTCHA on signup, known bot IPs blocked, Roblox moderation

**Layer 2 — Account Age Gates**
```
Earn XP from chat     → 7 days old
Group quests          → 7 days old
Trade items           → 14 days old
Gift items            → 14 days old
Subscribe for home    → 30 days OR email verified
```

**Layer 3 — Behavior Detection**
- Flag: 20 waves in 2 minutes, same message spammed, never moves, interacts with only 1 account
- 1st flag: social XP halved 24hrs | 2nd: locked 48hrs | 3rd: reported to Roblox

**Layer 4 — Interaction Validation**
- Both players must be moving
- Both must be different accounts
- Interactions must happen in different locations
- Must be within 5–15 studs (natural distance)
- 10 minute gap between same-player interactions

**Layer 5 — Human Proof Moments**
- Triggered by 500+ social XP in session or rapid identical actions
- Fun mini-checks: tap blue fruit, touch glowing root, basic game quiz
- Pass → "Verified Human" 2 hours | Fail → social XP paused 10 min

**Layer 6 — Social Graph Analysis**
- Track interaction networks
- Player A only interacts with Player B = suspicious
- Bot rings detected and all flagged simultaneously, XP reversed

---

## 14. TECHNICAL NOTES <a name="technical"></a>

### Chat System
- **Roblox TextChatService** handles all player chat (built-in, free)
- We create 2 custom channels: **Announcements** (read-only, global) and **Tower Chat** (residents only)
- Hunger Games announcements = `channel:DisplaySystemMessage()` — one line of code
- Profanity filter: automatic via Roblox (no work needed)

### Hunger Games Announcements (Examples)
```
🌳 THE TREE OF LIFE AWAKENS. 16 PLAYERS ENTER. ONLY 1 WILL REMAIN.
⚔️  [Player] eliminated [Player2]! 14 players remain.
💥 [Player] consumed the MAGMA FRUIT — all shall burn!
🌽 [Player] harvested a LEGENDARY Golden Carrot — fully healed!
⬆️  [Player] hit LEVEL 50 — WARLORD status achieved!
🏠 [Player] upgraded to BRICK HOUSE — looking fancy!
🔗 [Player] joined thanks to [Referrer]'s code! Welcome! 🌳
🚨 A RAID HAS BEGUN! THE TIDE KRAKEN RISES! 18:00 REMAINING!
👑 [Player] IS THE LAST LEGEND! THE TREE OF LIFE BOWS!
```

### DataStore Usage
- Player profile: level, XP, Leaves, Crown Gems, referral code, referral count
- Pet data: species, rarity, age stage, mastery, accessories
- Home data: pod assigned, floor number, garden crops + grow timers
- Brainrot collection: which characters owned
- Fruit/sword mastery: per-fruit mastery level
- Social data: unique players interacted with, daily caps
- Subscription status: checked via MarketplaceService

### Build Order (Recommended)
```
PHASE 1 — CORE WORLD
  □ Tree of Life (center anchor)
  □ Crystal Dome (glass sphere + 4 archways)
  □ 3 circular ring paths + 4 spoke paths
  □ 12 tower foundations + 1 template tower
  □ Clone tower × 11 around ring

PHASE 2 — NPC & QUESTS
  □ Elder Mira NPC + Quest 1 dialogue
  □ Pet egg selection + hatch animation
  □ Quest Board near dome
  □ Market stall + Bounty Board

PHASE 3 — GAME MODES
  □ Royal Rumble (10 min timer, zone collapse)
  □ Crown Run (4 stages)
  □ Dungeon (4 bosses)
  □ Announcement system

PHASE 4 — PROGRESSION
  □ XP bar + level HUD
  □ Leaves + Crown Gems HUD
  □ Daily login streak (DataStore)
  □ Match reward chests
  □ Pet aging + mastery

PHASE 5 — SOCIAL FEATURES
  □ Social XP interactions
  □ Group quest system
  □ Trading marketplace
  □ Stealing mechanic + defense
  □ Brainrot conveyor
  □ Vehicles

PHASE 6 — MONETIZATION SHELL
  □ Subscription check (MarketplaceService)
  □ Pod assignment on subscribe
  □ Robux shop UI (V1: "Coming Soon" placeholders)
  □ Referral system (unique codes + DataStore)
  □ Battle Pass UI placeholder
```

---

## 🎯 GAME IDENTITY SUMMARY

> **Life of Legends** is a Roblox social RPG where every player interaction matters.  
> You raise pets that age and evolve (Adopt Me), collect and steal Brainrot characters  
> from rivals (Steal a Brainrot), and master Devil Fruit powers to fight bosses and  
> dominate the world (Blox Fruits) — all within a living circular hub built around  
> the glowing Tree of Life. Every 10 minutes, chaos erupts in the Royal Rumble.  
> Every 45 minutes, a Raid threatens the world. Every day, your garden grows,  
> your pet evolves, and your tower pod becomes more yours.

---

*Document created: June 2026*  
*Next step: Begin Phase 1 build in Roblox Studio*
