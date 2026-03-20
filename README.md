# ⚠️ PROPRIETARY SOFTWARE - ALL RIGHTS RESERVED ⚠️

## 🚫 COPYRIGHT NOTICE - NO PERMISSIONS GRANTED

**THIS SOFTWARE IS THE EXCLUSIVE PROPERTY OF DCS**

- ❌ **NO MODIFICATION** - You may not modify, alter, or create derivative works
- ❌ **NO DISTRIBUTION** - You may not distribute, share, or redistribute this software
- ❌ **NO REPRODUCTION** - You may not reproduce or copy this software
- ❌ **NO COMMERCIAL USE** - You may not use this software for commercial purposes
- ❌ **NO DOWNLOADS** - You may not download or save copies of this software
- ❌ **NO FORKING** - You may not fork this repository
- ❌ **NO CONTRIBUTIONS** - You may not contribute code or submit pull requests

**This repository is for VIEWING ONLY. All rights reserved by DCS.**

---

# Runes of Tir na nÓg - Enhanced Prototype

**Feature-rich top-down RPG prototype with pixel art graphics and UI systems**

## 🎯 Overview

This is an enhanced prototype demonstrating advanced game development concepts:

- ✅ **60 FPS game loop** with delta time
- ✅ **Top-down camera** that follows the player
- ✅ **WASD movement** with collision detection
- ✅ **Procedural world** generation with pixel art textures
- ✅ **Health bar system** with visual heart indicators
- ✅ **Modular component architecture** for scalability
- ✅ **No external dependencies** (vanilla JavaScript only)
- ✅ **Optimized performance** with viewport culling
- ✅ **Multiplayer UI system** with username management
- ✅ **Server connection interface** with status indicators

## 📚 Documentation

| Doc | Purpose |
|-----|---------|
| [SUMMARY.md](SUMMARY.md) | Project status, feature inventory, roadmap notes |
| [CHANGELOG.md](CHANGELOG.md) | Version history |
| [SBOM.md](SBOM.md) | Runtime stack and dependency/security notes |
| [style_guide.md](style_guide.md) | UI theme and conventions |
| [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) | System architecture (detailed) |
| [docs/MULTIPLAYER_IMPLEMENTATION_PLAN.md](docs/MULTIPLAYER_IMPLEMENTATION_PLAN.md) | Multiplayer design notes |
| [docs/SCRATCHPAD.md](docs/SCRATCHPAD.md) | Agent session log and debug pointers |

## ▶️ Quick start

1. From the repo root, run `python server.py` (serves HTTP on port 8000 and starts the local WebSocket helper from `legacy-server/` when available).
2. Open `http://localhost:8000/` — you get `index.html` (username / landing).
3. Continue to `assets/menu.html`, then `game.html` for the canvas session (or use in-menu navigation).

## 🚀 Features

### Core Gameplay
- **Player Movement**: Smooth WASD controls
- **Collision Detection**: Prevents walking through walls
- **Camera System**: Follows player with smooth movement
- **World Rendering**: Only renders visible tiles for performance
- **Combat System**: Complete RPG combat with player and NPC attacks
- **Health System**: Above-character health bars with color-coded states
- **Floating Damage Numbers**: Animated damage numbers that float upward and fade out
- **Hostile NPCs**: Rats that chase and attack players with detection radius
- **Textured Ground**: Pixel art ground tiles with grass, dirt, and decorative elements
- **Inventory System**: Full RPG-style inventory with 8 equipment slots and 24 item slots
- **Water System**: Random water tiles with pixel art textures and audio feedback
- **Cave System**: Rare cave tiles (2% spawn) with dark cave textures

### Multiplayer UI System
- **Username Management**: Secure username input with validation and localStorage persistence
- **Server Connection**: Visual connection status with animated indicators
- **Menu Flow Integration**: Seamless navigation from landing page to main menu
- **Notification System**: Slide-in notifications for user feedback and status updates
- **Error Handling**: Comprehensive error messages with visual feedback
- **Consistent Styling**: Golden glow theme maintained across all UI elements

### Technical
- **Canvas Rendering**: Hardware-accelerated 2D graphics with pixel art support
- **Input Handling**: Keyboard and mouse support with 8-directional movement
- **Performance Monitoring**: Real-time FPS and memory usage display
- **Responsive Design**: Adapts to different screen sizes and zoom levels
- **Modular Architecture**: Clean separation of concerns with component-based design

## 🎮 Controls

### Movement
| Key | Action |
|-----|--------|
| W / ↑ | Move Up ✅ |
| S / ↓ | Move Down ✅ |
| A / ← | Move Left ✅ |
| D / → | Move Right ✅ |
| Shift | Sprint (1.5x speed) ✅ |
| Ctrl | Crouch (0.5x speed) ✅ |

### Game Controls
| Key | Action |
|-----|--------|
| ESC | Pause game ✅ |
| I | Open/Close Inventory ✅ |
| E | Interact with objects 🚧 |
| M | Main menu 🚧 |
| F1 | Toggle debug info ✅ |
| F12 | Take screenshot ✅ |

### Combat & Actions
| Key | Action |
|-----|--------|
| Space | Attack ✅ |
| Q | Block/Parry 🚧 |
| X | Dodge roll 🚧 |
| F | Use item 🚧 |
| 1-8 | Quick slots 🚧 |

### Camera & UI
| Key | Action |
|-----|--------|
| Mouse | Look around (click & drag) ✅ |
| Scroll Wheel | Zoom in/out ✅ |
| = / + | Zoom in 🚧 |
| - / _ | Zoom out 🚧 |
| 0 | Reset zoom 🚧 |
| C | Toggle camera lock 🚧 |
| J | Quest log 🚧 |
| P | Character panel 🚧 |
| N | World map 🚧 |
| T | Chat/Console 🚧 |

### Audio & Utility
| Key | Action |
|-----|--------|
| K | Toggle audio ✅ |
| ] / } | Volume up 🚧 |
| [ / { | Volume down 🚧 |
| ` | Developer console 🚧 |
| F11 | Toggle fullscreen 🚧 |

> **Note**: All keybinds can be customized in the Settings menu!
> 
> **Status Legend**: ✅ Implemented | 🚧 Coming Soon

## 🎒 Inventory System

The game features a comprehensive RPG-style inventory system with equipment management and item storage.

### Equipment Slots
- **Helmet** - Head armor protection
- **Necklace** - Accessory for special bonuses
- **Chest** - Body armor protection
- **Weapon** - Main weapon slot
- **Rings (2)** - Two ring slots for special effects
- **Legs** - Leg armor protection
- **Boots** - Foot armor protection

### Item Storage
- **24 Item Slots** - General inventory grid for storing items
- **Item Tooltips** - Hover over items to see detailed information
- **Visual Feedback** - Click items to select/use them
- **Sample Items** - Includes Health Potions, Iron Sword, Leather Armor, and Gold Ring

### Character Stats
The inventory displays your character's current stats:
- **⚔️ Attack** - Damage output
- **🛡️ Defense** - Damage reduction
- **💨 Speed** - Movement speed

### Resources
- **💰 Gold** - Currency tracking (currently 1,250 gold)
- **⚖️ Weight** - Inventory capacity tracking (12/50)

### UI Features
- Beautiful medieval-themed design with golden borders
- Pixel-perfect rendering matching game aesthetic
- Automatically pauses game when open
- Responsive layout that adapts to screen size
- Smooth animations and transitions

## ⚙️ Settings System

The game features a comprehensive settings menu with multiple categories:

### Video Settings
- **Render Distance**: Adjust how many tiles are rendered around the player (16x16 to 128x128)
- **Edge Fog Intensity**: Control fog effect at render distance edges (0% to 100%)
- **Grid Lines**: Toggle grid overlay on/off for better tile visibility

### Keybind Settings
- **Movement Controls**: WASD, Arrow Keys, Sprint, Crouch
- **Game Controls**: Pause, Inventory, Interact, Menu
- **Camera Controls**: Zoom in/out, Reset zoom, Camera lock
- **UI Controls**: Quest log, Character panel, Map, Chat
- **Combat Controls**: Attack, Block, Dodge, Use item
- **Quick Slots**: 8 customizable quick access slots
- **Utility Controls**: Screenshot, Debug, Console, Fullscreen
- **Audio Controls**: Toggle audio, Volume up/down

### Customization Features
- **Click to Rebind**: Click any keybind button to set a new key
- **Visual Feedback**: Animated buttons during key capture
- **Reset to Defaults**: One-click restore to original keybinds
- **Real-time Sync**: Video settings (like grid toggle) apply immediately without restart
- **Persistent Storage**: Settings saved automatically to browser storage
- **Category Navigation**: Easy switching between Video and Keybind settings

## 📊 Performance

- **File Size**: Optimized modular components (~15KB total)
- **Memory Usage**: < 10MB in browser with textures loaded
- **CPU Usage**: Minimal (60 FPS target maintained)
- **Network**: Game assets load from the app origin; HTML pages may load **Google Fonts** (Cinzel) for typography. Multiplayer uses **WebSockets** when enabled.
- **Rendering**: Viewport culling for optimal performance
- **Texture Loading**: Asynchronous with fallback systems

## 🔧 Technical Details

### Architecture
```
/ (repo root)
├── index.html              # Landing: username modal, link into menu
├── game.html               # Canvas game shell (single / multi), mobile controls, chat UI
├── server.py               # Local HTTP + spawns legacy WebSocket server
├── assets/
│   ├── menu.html           # Main menu, server status, world entry
│   └── world-selection.html
├── core/
│   ├── Game.js             # Main coordinator
│   ├── GameLoop.js         # 60 FPS loop
│   ├── main.js             # Bootstrap
│   ├── NetworkManager.js   # Multiplayer client
│   └── SaveSystem.js       # Save/load helpers
├── ui/
│   ├── UI.js, HealthBar.js, Inventory.js, PauseMenu.js
│   ├── SettingsPanel.js, VideoSettings.js, KeybindSettings.js, GameplaySettings.js
├── player/
│   ├── Player.js
│   └── NameTag.js
├── npc/
│   └── NPC.js              # Hostile NPCs (e.g. rats)
├── world/
│   └── World.js
├── camera/
│   └── Camera.js
├── input/
│   └── Input.js
├── audio/
│   └── AudioManager.js
├── utils/
│   └── SecurityUtils.js
├── legacy-server/
│   ├── multiplayer_server.py
│   └── requirements.txt    # websockets>=11.0.0
├── docs/                   # Architecture, security reports, SCRATCHPAD, plans
├── SUMMARY.md, SBOM.md, CHANGELOG.md, style_guide.md
└── README.md               # This file
```

### Engine Components
- **Game Loop**: RequestAnimationFrame-based 60 FPS with delta time
- **Rendering**: Canvas 2D with viewport culling and pixel art textures
- **Input**: Event-driven keyboard and mouse handling
- **Collision**: Tile-based detection with forgiving boundaries
- **Camera**: Smooth following with zoom and boundary constraints
- **Textures**: Pixel-perfect image rendering with retro aesthetics
- **UI System**: Modular health bar and debug information display
- **World Generation**: Procedural tile generation with texture support
- **Audio System**: Web Audio API with water sound effects and footstep audio

## 🧪 Testing Health Bar

The health bar can be tested using browser console commands:

```javascript
// Set health levels
testHealth.setFull()    // 10/10 hearts
testHealth.setHalf()    // 5/10 hearts  
testHealth.setLow()     // 2/10 hearts
testHealth.setEmpty()   // 0/10 hearts

// Dynamic changes
testHealth.damage(2)    // Take 2 damage
testHealth.heal(1)      // Heal 1 health
```

## 🎨 Ground Texture System

The game now features a pixel art ground texture system:

- **Textured Tiles**: Ground tiles now use the `Ground_Texture_1.png` pixel art texture
- **Pixel-Perfect Rendering**: Maintains retro aesthetics with crisp pixel art
- **Seamless Coverage**: Textures extend beyond world bounds for infinite appearance
- **Performance Optimized**: Only renders visible tiles with viewport culling

### Testing Ground System
```javascript
// Regenerate world with new texture system
regenerateWorld()       // Generate new world layout with textures
```

## 🔊 Audio System

The game features a Web Audio API-based sound system:

- **Water Sounds**: Procedurally generated water splashing sounds when walking on water tiles
- **Footstep Audio**: Basic footstep sounds for ground movement
- **Volume Control**: Adjustable audio levels
- **Audio Toggle**: Enable/disable audio system

### Testing Audio System
```javascript
// Audio testing commands
testAudio.playWater()        // Play water sound effect
testAudio.playFootstep()     // Play footstep sound
testAudio.setVolume(0.7)     // Set volume (0-1)
testAudio.toggleAudio()      // Toggle audio on/off
```

## 🕳️ Cave System

The game features rare cave tiles scattered throughout the world:

- **Cave Tiles**: 2% spawn rate with dark cave textures
- **Walkable**: Players can traverse cave tiles without collision
- **Pixel Art**: Dark brown and gray cave textures with rocky formations
- **Rare Spawn**: Makes cave discoveries feel special and rewarding

### World Tile Distribution
- **85%** - Grass tiles (with ground texture)
- **10%** - Water tiles (with water texture + audio)
- **3%** - Wall tiles (collision blocks)
- **2%** - Cave tiles (with cave texture)

## 🌐 Multiplayer System

The client includes a full **multiplayer UI** plus a **WebSocket client** (`core/NetworkManager.js`) for real-time play when a compatible server is reachable. Local development can use `server.py` together with `legacy-server/multiplayer_server.py` (see `legacy-server/README.md`). Production endpoints may be allow-listed in page CSP (`connect-src`) where used.

### Username Management
- **Secure Input**: Username validation with character restrictions
- **Persistence**: localStorage integration for session continuity
- **Visual Feedback**: Success/error states with color-coded indicators

### Server Connection UI
- **Status Indicators**: Animated connection status (disconnected/connecting/connected)
- **Join Server Button**: Blue-themed button with connection state management
- **Error Handling**: Comprehensive error messages and retry functionality

### Menu Flow Integration
- **Landing**: `index.html` username modal before entering main menu
- **Seamless Navigation**: Smooth transitions between UI states
- **Notification System**: Slide-in notifications for user feedback

### Implemented client features
- **WebSockets**: Connect flow and heartbeat-oriented handling in `NetworkManager.js`
- **Chat**: In-world chat bubbles (see `game.html` ChatManager) when connected
- **Multiplayer-aware pause**: Documented in `SUMMARY.md` / `docs/SCRATCHPAD.md`

## 🚀 Next Steps

High-value follow-ups (combat and core multiplayer client work are already in tree):

1. **Content** — Quests, dialogue NPCs, loot drops tied to inventory stats
2. **Persistence** — Extend `SaveSystem.js` for full world / multiplayer state if needed
3. **Polish** — Remaining keybind rows marked 🚧 in the tables above (block, dodge, map, etc.)
4. **Server ops** — Hardening, monitoring, and deployment docs for your chosen host
5. **Testing** — Automated checks for critical paths (input, network reconnect, save)

## 💡 Design Philosophy

- **Lightweight First**: Prove concepts work before adding complexity
- **Performance Focused**: 60 FPS target, minimal resource usage
- **Iterative Development**: Each phase adds one major system
- **Web Native**: Browser-only, no downloads required

---

*"Sometimes the best way to start is with something so simple, it can't possibly fail."*
