🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

```
███████╗ ██████╗  ██████╗     ██████╗ ██████╗ ███████╗
██╔════╝██╔═══██╗██╔════╝    ██╔═══██╗██╔══██╗██╔════╝
███████╗██║   ██║██║  █████╗██║   ██║██████╔╝███████╗
╚════██║██║   ██║██║  ╚════╝██║   ██║██╔═══╝ ╚════██║
███████║╚██████╔╝╚██████╗    ╚██████╔╝██║     ███████║
╚══════╝ ╚═════╝  ╚═════╝     ╚═════╝ ╚═╝     ╚══════╝
                                                        
    🕹️  SOCIAL BINGO ARCADE STATION  🕹️
        [INSERT C0I N T0 C0NTINUE]
```

---

## 📺 THE GAME

**Find humans. Mark squares. WIN BIG.**

A retro-style social bingo arcade cabinet for mixers, team-building events, and anywhere humans need to actually talk to each other. Read the prompts, hunt down the players, tap the squares, get **FIVE IN A ROW** for:

```
    ████████████████████
    █ * P O I N T S * █
    ████████████████████
```

🎮 Built in **BLAZOR WebAssembly** | 🔷 **.NET 10 Runtime** | 📦 **Zero CSS dependencies** | 💾 **Level saves to localStorage**

---

## 🎯 COIN SLOTS

### ▶ PLAY NOW
**[⚡ LAUNCH THE ARCADE](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/)**  
No quarters needed. No installation. Just click and compete.

### 🏫 LEARN THE ROPES
Follow the **[ARCADE MANUAL](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/)** — 5 levels of pure development mastery:

```
LEVEL 00 │ ▌ % │ ◆ PROJECT SETUP & SURVIVAL GUIDE
LEVEL 01 │ ▌ # │ ◆ CONTEXT ENGINEERING & AI PARTNERS  
LEVEL 02 │ ▌ & │ ◆ PIXEL-PERFECT FRONTEND DESIGN
LEVEL 03 │ ▌ @ │ ◆ QUIZ MASTER AGENT UNLOCKED
LEVEL 04 │ ▌ $ │ ◆ MULTI-AGENT FINAL BOSS
```

🖥️ **Offline mode?** All manuals cached in [`workshop/`](workshop/) folder—play without internet!

---

## ⭐ POWER-UPS

```
[✓] Conversation Igniter    - Real icebreakers, zero awkward silence
[✓] Plug & Play             - Launch immediately, no tweaking
[✓] Themeable               - Customize questions for YOUR crowd
[✓] Dev Masterclass         - Learn real Blazor patterns & C# state
[✓] Source Code Open        - Fork it. Hack it. Make it yours.
```

---

## ▶ GAMEPLAY MECHANICS

```
┌──────────────────────────────┐
│ STAGE 1: READ THE PROMPT     │
├──────────────────────────────┤
│ STAGE 2: FIND THAT HUMAN     │
├──────────────────────────────┤
│ STAGE 3: TAP THE SQUARE      │
├──────────────────────────────┤
│ STAGE 4: FIVE IN A ROW?      │
│         ► YES = HIGH SCORE!  │
└──────────────────────────────┘
```

---

## � ARCADE ROM SETUP (For Developers)

### 🎮 System Requirements
```
CPU: .NET 10 SDK or higher
RAM: 512MB minimum
INPUT: Keyboard, Mouse, or Touch
DISPLAY: Modern browser (Chrome, Firefox, Safari, Edge)
```

📥 **[Download .NET 10](https://dotnet.microsoft.com/download/dotnet/10.0)**

---

### ▶ START YOUR LOCAL CABINET

```bash
# Clone the arcade code
git clone <your-repo>
cd my-soc-ops-csharp

# Boot up the emulator
cd SocOps
dotnet run
```

🎯 Game launches on **`http://localhost:5166`**

---

### 🏗️ BUILD YOUR CUSTOM ROM

```bash
# Compile the cartridge
dotnet build

# Master archive build  
dotnet publish
```

✅ **Auto-deployment:** Every `main` branch push → **GitHub Pages** (no manual steps)

---

## 🌐 PLAY IN THE CLOUD (GitHub Codespaces)

No arcade cabinet needed. Play in the browser:

1. Fork this repo on GitHub
2. Click **Code** → **Codespaces** → **Create codespace on main**
3. Wait for the devcontainer genesis sequence to complete
4. In the terminal:
   ```bash
   cd SocOps
   dotnet run
   ```

**Boom.** Instant browser arcade. No installation. Pure cloud gaming.

---

## 🗂️ ARCADE SCHEMATICS

```
SocOps/
├── Components/          ◆ The Pixels (UI Cabinet)
│   ├── BingoBoard.razor      ✦ 5×5 Grid Controller
│   ├── GameScreen.razor       ✦ Main Arcade Display
│   └── StartScreen.razor      ✦ Cabinet Boot Screen
│
├── Services/            ◆ The Logic (CPU)
│   ├── BingoGameService.cs      ✦ State Manager
│   └── BingoLogicService.cs     ✦ Game Rules Engine
│
├── Models/              ◆ The Data (Memory)
│   ├── GameState.cs
│   ├── BingoSquareData.cs
│   └── BingoLine.cs
│
├── Pages/               ◆ The Router (Navigation)
└── wwwroot/css/app.css  ◆ The Shaders (Custom styling)
```

### 🎨 Design Patterns Unlocked:
- **Component Architecture** — Modular, reusable Blazor parts
- **Immutable State** — Predictable game updates (no mutations!)
- **Level Persistence** — localStorage auto-saves your progress
- **Pure Logic** — `BingoLogicService` = zero side effects, 100% testable

---

## 📚 ARCADE MANUAL (Full Developer Guide)

Deep dive into each level:

🎯 **[Level 00](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=00-overview)** — Project anatomy & survival checklist  
🎯 **[Level 01](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=01-setup)** — Environment setup & AI-assisted coding  
🎯 **[Level 02](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=02-design)** — CSS mastery & component design  
🎯 **[Level 03](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=03-quiz-master)** — Custom question generation with AI  
🎯 **[Level 04](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=04-multi-agent)** — Advanced multi-agent orchestration  

📖 Cached offline in [`workshop/`](workshop/) — no internet, no problem.

---

## 🤝 PLAYER CONTRIBUTIONS

Found a bug? Have a power-up idea? Wanna add new cabinet themes? **Jump in:**

1. 🐛 **Report Glitches** — [Open an issue](../../issues) with full specs  
2. 💡 **Suggest Features** — Question packs, themes, gameplay modes  
3. 🔧 **Submit Mods** — Fork → Create feature branch → PR  
4. 📖 **Improve Docs** — Make the manual clearer for next players  

Read [CONTRIBUTING.md](CONTRIBUTING.md) for the full ruleset.

---

## ⚖️ LICENSE & ATTRIBUTION

```
████████████════════════════════════
  MIT License - Do Whatever You Want
████████████════════════════════════
```

Use it. Learn from it. Remix it. Share it. [Full license text](LICENSE).

---

## 🎊 KEEP THE ARCADE ALIVE

```
[★] Star this repo for cosmic luck
[↗] Share with your crew—spread the word
[💬] Give feedback in Issues
[🚀] Build YOUR custom cabinet—show us!
```

---

## ❓ GAME OVER? GET HELP

Stuck? Check [SUPPORT.md](SUPPORT.md) for tutorials, FAQs, and community links.

```
╔════════════════════════════════╗
║        Thanks for Playing!     ║
║   [PRESS START TO CONTINUE]    ║
╚════════════════════════════════╝
```
