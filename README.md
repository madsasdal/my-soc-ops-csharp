🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

# 🎯 Soc Ops: Social Icebreaker Bingo

Break the ice and build real connections—one bingo square at a time!

**Soc Ops** is a fun, interactive social bingo game designed for mixers, team-building events, workshops, and anywhere people need to connect. Players find individuals who match icebreaker prompts, mark their squares, and race to get five in a row. It's engaging, memorable, and designed to spark genuine conversations.

**Built with:** Blazor WebAssembly + .NET 10 | **No external CSS frameworks** | **Persistent game state** | **Perfect for learning full-stack development**

---

## 🚀 Quick Start

### Play Now
👉 **[Launch the Live Game](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/)**

### Learn by Building
Want to build your own version? Follow our interactive **[Dev Lab Guide](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/)** — a hands-on workshop that teaches you:

| Module | What You'll Learn |
|--------|-------------------|
| [**Module 00**](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=00-overview) | Project overview & development checklist |
| [**Module 01**](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=01-setup) | Setup, context engineering & AI-assisted development |
| [**Module 02**](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=02-design) | Design-first frontend development with custom CSS |
| [**Module 03**](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=03-quiz-master) | Create custom question sets with AI agents |
| [**Module 04**](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/step.html?step=04-multi-agent) | Multi-agent workflows & advanced patterns |

📖 **Prefer local docs?** All guides are in the [`workshop/`](workshop/) folder for offline learning.

---

## ✨ Why Soc Ops?

✅ **Icebreaker Perfected** — Thoughtfully designed prompts spark real conversations, not awkward silence  
✅ **Zero Setup** — Just launch and play—no installation needed  
✅ **Customizable** — Modify questions and themes for your event  
✅ **Learn Modern Dev** — Great example of Blazor component architecture, state management, and UI/UX design  
✅ **Open Source** — Fork, customize, and contribute  

---

## 🎮 How to Play

1. **Start the game** — Click "Play" to begin
2. **Find matches** — Read the prompts and find someone who matches each square
3. **Mark squares** — Tap a square when found
4. **Win** — Get 5 in a row (horizontal, vertical, or diagonal) to win!

---

## 💻 For Developers

### Prerequisites
- [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0) or higher

### Get Started Locally

```bash
# Clone and navigate to the project
git clone <your-repo>
cd my-soc-ops-csharp

# Run the development server
cd SocOps
dotnet run
```

The game will be available at `http://localhost:5166`

### Build & Deploy

```bash
# Build the project
dotnet build

# Publish for production
dotnet publish
```

Deployments to GitHub Pages happen automatically on every push to `main`.

---

## 🐙 Develop in GitHub Codespaces

Want to code without installing anything? Use GitHub Codespaces:

1. Fork this repo on GitHub
2. Click **Code** → **Codespaces** → **Create codespace on main**
3. Wait for the dev container to finish setup
4. From the repository root:
   ```bash
   cd SocOps
   dotnet run
   ```

The dev container comes pre-configured with .NET 10, all dependencies, and dev tools.

---

## 🏗️ Project Structure

```
SocOps/
├── Components/           # Blazor components (UI)
│   ├── BingoBoard.razor
│   ├── GameScreen.razor
│   └── StartScreen.razor
├── Services/             # Business logic
│   ├── BingoGameService.cs      (state management)
│   └── BingoLogicService.cs     (game rules)
├── Models/               # Data models
├── Pages/                # Route pages
└── wwwroot/              # Static assets & CSS
```

**Architecture highlights:**
- **Component-based UI** — Reusable, testable Blazor components
- **Immutable state** — Predictable updates via services
- **Local persistence** — Game state saved to localStorage
- **Custom CSS** — No external frameworks; pure, optimized styling

---

## 🎓 Learn More

Want to understand how it works? The **[Lab Guide](https://dotnet-presentations.github.io/vscode-github-copilot-agent-lab/docs/)** walks you through:

- Setting up context for AI-assisted development
- Building components with design-first thinking
- Managing game state with C# services
- Customizing questions and gameplay with AI agents
- Advanced patterns with multiple agents

---

## 🤝 Contributing

We love contributions! Here's how to help:

1. **Report bugs** — Open an issue with details
2. **Suggest features** — Share ideas for new question packs or themes
3. **Submit PRs** — Fork, create a feature branch, and submit a pull request
4. **Improve docs** — Help make the workshop clearer

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## 📝 License

This project is licensed under the [MIT License](LICENSE)—feel free to use it for learning, teaching, and building your own versions.

---

## 🙌 Support this Project

- **⭐ Star** this repo if you found it helpful
- **🔄 Share** it with your team or event organizers
- **💬 Give feedback** via GitHub issues
- **🚀 Deploy your own** version—show us what you build!

---

**Questions?** Check out [SUPPORT.md](SUPPORT.md) for help resources.
