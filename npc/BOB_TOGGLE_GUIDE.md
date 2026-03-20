# Bob NPC Toggle - User Guide

**Version**: 0.5.5  
**Date**: October 19, 2025  
**Feature**: Gameplay Settings with Bob Control

---

## Overview

You now have full control over whether Bob NPC spawns in your game! This is managed through the new **Gameplay Settings** panel.

---

## How to Use

### Accessing Settings

1. **From Main Menu**:
   - Open the site root (`http://localhost:8000/` → `index.html`), then open the main menu (`assets/menu.html`)
   - Click the **⚙️ Settings** button

2. **Navigate to Gameplay**:
   - In the settings panel, you'll see three tabs:
     - 🖥️ **Video** (render distance, fog)
     - 🎮 **Gameplay** ← Click this one!
     - ⌨️ **Keybinds** (controls)

### Bob Toggle

In the Gameplay settings, you'll find:

```
┌─────────────────────────────────────┐
│ 🎮 Gameplay Settings                │
├─────────────────────────────────────┤
│                                     │
│ Bob NPC Character:                  │
│ ┌───────────┐  Enabled              │
│ │  ○→       │                       │
│ └───────────┘                       │
│                                     │
│ Enable/disable Bob, the wandering   │
│ NPC. Bob will spawn randomly in     │
│ new worlds when enabled.            │
│                                     │
│ Note: Requires starting a new game  │
│ to take effect.                     │
└─────────────────────────────────────┘
```

### Toggle States

**Enabled (Default)**:
- Toggle switch is **GOLD** colored
- Slider is on the **RIGHT**
- Status shows "**Enabled**"
- Bob will spawn in new games

**Disabled**:
- Toggle switch is **GRAY** colored
- Slider is on the **LEFT**
- Status shows "**Disabled**"
- Bob will NOT spawn in new games

### Saving Settings

1. After changing the toggle, click **💾 Save Settings**
2. You'll see a confirmation:
   ```
   Settings saved!
   
   Bob NPC: Enabled
   NPC Density: 100%
   
   Restart your game for changes to take effect.
   ```
3. Close the settings panel
4. **Start a new game** for changes to apply

---

## Important Notes

### ⚠️ Requires New Game

Bob spawning is determined when the world is created. Changing the setting does **NOT** affect existing save games. You must:

1. Change the setting
2. Save settings
3. **Start a NEW game**

### Default Behavior

If you've never touched the setting:
- Bob is **ENABLED** by default
- Bob will spawn in all new games
- You can disable him anytime

### Finding Bob

When Bob spawns, check the console (F12) for:
```
✅ Bob NPC spawned (setting: enabled)
Spawning Bob at (2847, 1423)
```

Navigate to those coordinates to find him!

If disabled:
```
❌ Bob NPC not spawned (setting: disabled)
```

---

## NPC Density (Future Feature)

You'll also see an "NPC Spawn Density" slider:

```
NPC Spawn Density:
┌─────────────────────────────┐
│  ○                          │  100%
└─────────────────────────────┘
0%                         200%
```

**Current Status**: Placeholder for future NPCs

- **0%**: No NPCs spawn (including Bob if enabled)
- **100%**: Default spawn rates
- **200%**: Double NPCs

Currently, this only affects Bob on/off. Once more NPCs are added (townies, merchants, guards), this slider will control how many spawn.

---

## Technical Details

### How It Works

1. **Setting Storage**: Your choice is saved to `localStorage.bobEnabled`
2. **World Creation**: When `Game.js` initializes NPCs, it checks this setting
3. **Spawn Logic**:
   ```javascript
   const bobEnabled = localStorage.getItem('bobEnabled');
   const shouldSpawnBob = bobEnabled === null ? true : bobEnabled === 'true';
   
   if (shouldSpawnBob) {
       // Spawn Bob at random location
   } else {
       // Skip Bob spawning
   }
   ```

### Files Involved

- **Settings UI**: `game/ui/GameplaySettings.js`
- **Settings Panel**: `game/ui/SettingsPanel.js`
- **Spawn Logic**: `game/core/Game.js` (initializeNPCs method)
- **Bob Config**: `game/npc/NPCConfig.js`

---

## Troubleshooting

### Bob Still Spawns After Disabling

**Cause**: You're playing an old save game  
**Solution**: Start a completely new game

### Toggle Doesn't Save

**Cause**: localStorage might be disabled/full  
**Solution**: 
1. Check browser console for errors
2. Clear site data and try again
3. Make sure localStorage is enabled

### Can't Find Settings Button

**Location**: Main menu (`assets/menu.html`)  
**Path**: `http://localhost:8000/assets/menu.html` (after username flow on `index.html`)  
**Not available in-game** (no pause menu settings yet)

---

## Future Enhancements

Planned additions to Gameplay Settings:

1. **Difficulty Settings**
   - Enemy spawn rate
   - Damage multiplier
   - Loot drop rate

2. **World Settings**
   - Biome selection
   - Structure density
   - Resource abundance

3. **NPC Settings**
   - Individual NPC toggles (Bob, townies, merchants, guards)
   - NPC density actually implemented
   - Friendly/hostile ratio

4. **Quality of Life**
   - Auto-save interval
   - Show coordinates
   - Debug mode toggle

---

## Related Documentation

- **Bob Implementation**: `game/npc/BOB_IMPLEMENTATION.md`
- **World Gen Analysis**: `game/WORLDGEN_UI_ANALYSIS.md`
- **NPC System**: `game/npc/README.md`
- **Settings Architecture**: See WORLDGEN_UI_ANALYSIS.md → UI System section

---

## Quick Reference

| Action | Steps |
|--------|-------|
| **Enable Bob** | Settings → Gameplay → Toggle ON → Save → New Game |
| **Disable Bob** | Settings → Gameplay → Toggle OFF → Save → New Game |
| **Find Bob** | F12 Console → Look for spawn coordinates |
| **Check Setting** | F12 Console → `localStorage.getItem('bobEnabled')` |
| **Reset to Default** | F12 Console → `localStorage.removeItem('bobEnabled')` |

---

**Enjoy controlling your Bob experience!** 🎮

For questions or issues, check the console logs or refer to the technical documentation.

