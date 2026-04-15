# Copilot Workspace Instructions

## Project Overview

**Soc Ops** is a Social Bingo game built with Blazor WebAssembly (.NET 10). Players find people who match icebreaker questions to mark squares and achieve 5 in a row (bingo).

**Stack**: C# + Blazor WebAssembly + .NET 10 + Custom CSS utilities

**Quick Links**:
- 🎮 [Play the live game](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/)
- 📚 [Workshop guides](./workshop/) - 5 learning modules (setup, design, quiz master, multi-agent)
- 🎯 [Lab guide](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/)

---

## Essential Architecture

```
SocOps/
├── Components/              # Reusable Blazor components
│   ├── BingoBoard.razor     # 5x5 grid, renders squares
│   ├── BingoSquare.razor    # Individual square with click handler
│   ├── BingoModal.razor     # Victory animation
│   ├── GameScreen.razor     # Main game UI
│   └── StartScreen.razor    # Initial screen
├── Services/                # Business logic & state
│   ├── BingoGameService.cs  # State management, localStorage persistence
│   └── BingoLogicService.cs # Game rules (board generation, bingo detection)
├── Models/                  # Data structures
│   ├── GameState.cs         # Enum: Start, Playing, Bingo
│   ├── BingoSquareData.cs   # Square model
│   └── BingoLine.cs         # Winning line model
├── Data/                    # Static data
│   └── Questions.cs         # 24 icebreaker questions
├── Pages/                   # Routable Blazor pages
│   └── Home.razor           # Entry point
└── wwwroot/                 # Static assets
    ├── index.html
    └── css/app.css          # Custom utility classes
```

### Key Design Decisions

| Decision | Why |
|----------|-----|
| **Component-based UI** | Blazor naturally encourages small, reusable components |
| **Immutable state updates** | BingoLogicService returns new lists (prevents bugs) |
| **localStorage persistence** | Game state survives page reloads via JSInterop |
| **Fisher-Yates shuffle** | Fair randomization of question selection |
| **Custom CSS utilities** | No external dependencies, lightweight, Tailwind-like |

---

## Development Workflow

### Build & Run

```bash
# From repository root
cd SocOps

# Watch & live reload (best for development)
dotnet run

# Just build
dotnet build

# Build for production
dotnet publish
```

**Dev server runs on**: `http://localhost:5166`

### Naming Conventions

| Category | Convention | Example |
|----------|-----------|---------|
| **Classes** | PascalCase | `BingoGameService`, `BingoSquareData` |
| **Methods** | PascalCase | `CheckBingo()`, `GenerateBoard()` |
| **Properties** | PascalCase | `CurrentGameState`, `WinningLine` |
| **CSS classes** | lowercase-kebab | `.bg-marked`, `.flex-col`, `.gap-2` |
| **Component files** | PascalCase.razor | `GameScreen.razor` |

### Code Style

- `using` directives at top, no System.Collections for LINQ
- Blank line before namespace declaration
- Comments for public methods (doc-style `///`)
- LINQ preferred over loops for collections
- Event handlers as `On*` methods in parent component

---

## Styling & CSS

**See**: [css-utilities.instructions.md](./instructions/css-utilities.instructions.md)

### Quick Palette

```css
Primary:   #0066CC (--accent)
Success:   #22C55E (green, marked squares)
Warning:   #F59E0B (amber)
Neutral:   #E5E7EB (gray-100)
Text:      #1F2937 (gray-900)
```

**Key utilities**:
- `flex`, `flex-col`, `grid`, `grid-cols-5`
- `gap-2`, `p-4`, `mb-2`, `mx-auto`
- `bg-white`, `bg-accent`, `bg-marked`
- `text-xl`, `font-bold`, `text-center`

---

## Frontend Design

**See**: [frontend-design.instructions.md](./instructions/frontend-design.instructions.md)

Apply this skill when designing new UI components or pages. Emphasizes:
- Distinctive typography and color choices
- Intentional motion and micro-interactions
- Avoiding generic "AI slop" aesthetics
- Context-specific, creative design decisions

---

## State Management Pattern

```csharp
// BingoGameService manages all game state
public GameState CurrentGameState { get; private set; }
public List<BingoSquareData> Board { get; private set; }

// Components subscribe to state changes
protected override void OnInitialized()
{
    GameService.OnStateChanged += StateHasChanged;
}

// Handlers update state and notify subscribers
public void HandleSquareClick(int squareId)
{
    Board = BingoLogicService.ToggleSquare(Board, squareId);
    // Check for bingo...
    NotifyStateChanged();
}
```

**Key points**:
- Never mutate `Board` directly; always return a new list
- State persists to localStorage automatically
- `OnStateChanged` event triggers component re-renders
- Services are scoped in `Program.cs`

---

## Common Pitfalls

| Pitfall | Solution |
|---------|----------|
| Mutating Board directly | Always return new lists from BingoLogicService |
| Forgetting `NotifyStateChanged()` | UI won't update; test with dev server reload |
| localStorage sync issues | Check browser DevTools → Application tab |
| Styling not applying | Verify CSS class name case (lowercase-kebab for utility) |
| Questions list not shuffling | Check Fisher-Yates seed; use `new Random()` per call |

---

## Workshop Structure

Located in `./workshop/`:

| Module | Focus |
|--------|-------|
| **00-overview.md** | Project scope, team coordination |
| **01-setup.md** | This checklist + context engineering |
| **02-design.md** | Design-first approach for UI |
| **03-quiz-master.md** | Custom quiz mode implementation |
| **04-multi-agent.md** | Multi-agent collaboration patterns |
| **05-complete.md** | Full solution reference |

Each module has `.md` and HTML versions for offline reading.

---

## Testing

No unit tests in the starter template, but the codebase is structurally testable:

- `BingoLogicService` methods are pure (stateless, deterministic)
- `BingoGameService` can be mocked in tests
- Components can be tested via Blazor.Component.Testing

Consider adding tests as features expand (especially bingo detection logic).

---

## Performance Notes

- **Minimal re-renders**: Only subscribed components re-render on state change
- **localStorage**: Max ~5MB; game state << 1KB, no issue
- **Bundle size**: No external CSS frameworks (custom utilities kept small)
- **Interop calls**: Minimal JSInterop usage (only for localStorage)

---

## Environment

- **OS**: Linux (Ubuntu 24.04 in devcontainer)
- **Runtime**: .NET 10 WebAssembly
- **Package manager**: NuGet (implicit via dotnet CLI)
- **Browser**: Supports all modern browsers

---

## Before Committing

```bash
cd SocOps

# Build check
dotnet build

# No test suite yet, so manual verification:
# 1. Run dev server: dotnet run
# 2. Test game flow: Start → Click squares → Achieve bingo
# 3. Verify persistence: Reload page, state restored
# 4. Check styling: All components render correctly
```

---

## Getting Help

- **Blazor docs**: https://learn.microsoft.com/en-us/aspnet/core/blazor/
- **.NET 10 WebAssembly**: https://learn.microsoft.com/en-us/dotnet/core/whats-new/dotnet-10
- **Workshop guides**: See `./workshop/GUIDE.md`
- **Repository issues**: Search existing GitHub issues first

---

## Suggested Next Steps

1. **Understanding the codebase**: Review `SocOps/Services/BingoLogicService.cs` (game rules)
2. **Styling customization**: Edit `SocOps/wwwroot/css/app.css` (colors, spacing)
3. **Feature expansion**: See workshop modules 03-04 for multi-mode support
4. **Testing**: Add unit tests for `BingoLogicService` methods
