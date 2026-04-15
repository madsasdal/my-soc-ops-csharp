# Copilot Workspace Instructions

## ✅ Mandatory Development Checklist

Before committing code:

```bash
cd SocOps

# 1. Lint/Format
dotnet format

# 2. Build
dotnet build

# 3. Test (manual until tests added)
# - Run: dotnet run
# - Test game flow: Start → Click squares → Achieve bingo
# - Verify persistence: Reload page, state restored
```

**Linting Rules** (`.editorconfig`):
- `dotnet_code_quality_unused_parameters = all:warning` — Unused variables/parameters
- `csharp_style_unused_private_member = true:warning` — Unused private members
- `csharp_style_prefer_async_over_sync = true:warning` — Prefer async over sync
- Use `_ = SaveGameStateAsync();` for "fire and forget" async calls

---

## Project Overview

**Soc Ops**: Social Bingo game (Blazor WebAssembly + .NET 10)  
Players find people matching icebreaker questions, mark squares, get 5 in a row to win.

**Quick Links**: [Live game](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/) • [Workshop](./workshop/) • [Lab guide](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/)

---

## Architecture

```
SocOps/
├── Components/              # BingoBoard, BingoSquare, GameScreen, StartScreen
├── Services/                # BingoGameService (state), BingoLogicService (rules)
├── Models/                  # GameState, BingoSquareData, BingoLine
├── Data/                    # Questions.cs (24 icebreaker questions)
├── Pages/                   # Home.razor (entry point)
└── wwwroot/css/app.css     # Custom utility classes (no external CSS)
```

**Key decisions**: Component-based UI, immutable state updates, localStorage persistence, Fisher-Yates shuffle, custom CSS utilities.

---

## Dev Workflow

```bash
cd SocOps
dotnet run              # Dev server on http://localhost:5166
dotnet build            # Build only
dotnet publish          # Production build
```

### Code Conventions

| Item | Style | Example |
|------|-------|---------|
| Classes/Methods | PascalCase | `BingoGameService`, `CheckBingo()` |
| Properties | PascalCase | `CurrentGameState`, `WinningLine` |
| CSS classes | kebab-case | `.bg-marked`, `.flex-col`, `.gap-2` |
| Components | PascalCase.razor | `GameScreen.razor` |

**Style**: Using directives at top, doc comments `///` for public methods, LINQ over loops, event handlers as `On*`.

---

## State Management

```csharp
// BingoGameService = central state hub
public GameState CurrentGameState { get; private set; }
public List<BingoSquareData> Board { get; private set; }

// Components subscribe: GameService.OnStateChanged += StateHasChanged;
// Service updates: Board = BingoLogicService.ToggleSquare(...); NotifyStateChanged();
```

**Rules**: Never mutate `Board` directly—always return new lists. Persist to localStorage automatically. `OnStateChanged` triggers re-renders.

---

## Styling

**Colors** (in `wwwroot/css/app.css`):
- Primary: `#0066CC` (--accent)
- Success: `#22C55E` (marked squares)
- Warning: `#F59E0B`
- Text: `#1F2937`

**Key utilities**: `flex`, `flex-col`, `grid`, `grid-cols-5`, `gap-2`, `p-4`, `mb-2`, `bg-white`, `bg-accent`, `text-xl`, `font-bold`

See [css-utilities.instructions.md](./instructions/css-utilities.instructions.md) and [frontend-design.instructions.md](./instructions/frontend-design.instructions.md).

---

## Common Pitfalls

| Issue | Fix |
|-------|-----|
| Mutating Board directly | Return new lists from BingoLogicService |
| UI not updating | Call `NotifyStateChanged()` after state changes |
| localStorage sync issues | Check DevTools → Application tab |
| Styles not applying | Use lowercase-kebab CSS class names |
| Questions not randomizing | Each call needs fresh `new Random()` |
| Async linting warnings | Use `_ = MethodAsync();` for fire-and-forget |

---

## Testing

No unit tests yet, but `BingoLogicService` is pure and testable. Components can use `Blazor.Component.Testing`. Add tests as features expand.

---

## Performance

- Minimal re-renders (only subscribed components)
- localStorage: ~5MB max; game state << 1KB
- Bundle size: No external CSS frameworks
- JSInterop: Only for localStorage

---

## Getting Help

- [Blazor docs](https://learn.microsoft.com/en-us/aspnet/core/blazor/)
- [.NET 10](https://learn.microsoft.com/en-us/dotnet/core/whats-new/dotnet-10)
- [Workshop modules](./workshop/) (5 learning guides)
- Search existing [GitHub issues](https://github.com/madsasdal/my-soc-ops-csharp/issues)

---

## Next Steps

1. Review `SocOps/Services/BingoLogicService.cs` (game rules)
2. Customize `SocOps/wwwroot/css/app.css` (colors, spacing)
3. Expand with multi-mode support (study workshop modules 03-04)
4. Add unit tests for `BingoLogicService` methods
