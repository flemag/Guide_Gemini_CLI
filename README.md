
<div align="center">

# 🚀 Guide Ultra-Complet — Gemini CLI

**Tout ce que vous devez savoir pour maîtriser Gemini CLI, l'agent IA open-source de Google pour le terminal.**

[![Open Source](https://img.shields.io/badge/Open_Source-✓-34a853?style=for-the-badge&logo=google&logoColor=white)](https://github.com/google-gemini/gemini-cli)
[![2026 Ready](https://img.shields.io/badge/2026-Ready-4285f4?style=for-the-badge&logo=google-gemini&logoColor=white)](https://ai.google.dev/)
[![Langue](https://img.shields.io/badge/Langue-Français-fbbc04?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-ea4335?style=for-the-badge)](./LICENSE)

---

[🇫🇷 Français](#) · [🇬🇧 English](#-english-version) · [🌟 Démo en ligne](#-aperçu) · [📖 Guide complet](./guide-gemini-cli.html)

*De zéro à expert — Installation, configuration avancée, commandes, outils intégrés, cas d'usage réels et cheat sheet.*

</div>

---

## ✨ Ce que vous trouverez

| Catégorie | Contenu |
|---|---|
| 🔧 **Installation & Auth** | Installation globale, npx, authentification sécurisée (1Password CLI, .env), premier lancement |
| ⌨️ **Commandes** | Toutes les slash commands (`/compress`, `/clear`, `/stats`, `/chat save`, `/chat resume`, `/restore`, `/init`, `/mcp`…), flags CLI (`-p`, `-m`, `--sandbox`, `--yolo`, `--checkpointing`, `--json`), raccourcis clavier |
| 📎 **@ Contextes Multimodaux** | Référencement de fichiers, images, audio/vidéo, répertoires avec `@./path` |
| ⚙️ **Configuration** | `settings.json` (3 niveaux), `GEMINI.md` hiérarchique (Global + Projet + Sous-répertoire), `.geminiignore`, commandes personnalisées TOML |
| 🔌 **MCP (Model Context Protocol)** | Configuration MCP dans settings.json, `gemini mcp add`, transports Stdio/SSE/HTTP, options détaillées |
| 🛠️ **Outils Intégrés** | `read_file`, `write_file`, `replace`, `search_file_content`, `list_directory`, `glob`, `google_web_search`, `web_fetch`, `save_memory`, `run_shell_command` |
| 🚀 **Fonctionnalités Avancées** | Code Interpreter/Sandbox, Google Search Grounding, Checkpointing & Restore, Mode Headless, Extensions, Model Routing, Intégration VS Code, Git Worktrees |
| 💡 **Conseils Pro** | Chain of Thought, Few-Shot Prompting, Prompts mauvais vs bons, gestion de sessions |
| 🎯 **8 Cas d'Usage Réalistes** | UI depuis maquette, Audit sécurité, Migration framework, Documentation auto, MCP Server custom, CI/CD Review, Tutoriel interactif, Analyse de logs |
| 📋 **Cheat Sheet** | Tableau récapitulatif express de toutes les commandes essentielles |

---

## 🖼️ Aperçu

Le guide est une **page web unique** au design sombre et moderne, avec :

- 🎨 Interface dark mode avec dégradés et effets de glow
- 🧭 Navigation flottante sticky pour un accès rapide aux sections
- 📋 Boutons de copie sur chaque bloc de code
- 🔽 Accordéons pour le contenu détaillé (MCP, options avancées)
- ✨ Animations au scroll (fade-in)
- 📱 Entièrement responsive (mobile, tablette, desktop)
- ⬆️ Bouton scroll-to-top
- 📊 Tableaux de comparaison visuels (prompts mauvais vs bons)

> Ouvrez simplement le fichier [`guide-gemini-cli.html`](./guide-gemini-cli.html) dans votre navigateur — aucune dépendance, aucun build, ça marche partout.

---

## 🚀 Quick Start

```bash
# Cloner le dépôt
git clone https://github.com/<votre-user>/guide-gemini-cli.git
cd guide-gemini-cli

# Ouvrir le guide dans votre navigateur
# macOS
open guide-gemini-cli.html
# Linux
xdg-open guide-gemini-cli.html
# Windows
start guide-gemini-cli.html
```

C'est tout. Le fichier est autonome — HTML + CSS + JS en un seul fichier, aucune installation requise.

---

## 📑 Table des matières du guide

Le guide couvre l'intégralité de Gemini CLI en **9 sections** :

1. **Installation & Authentification** — npm, npx, variables sécurisées, .env, premier lancement
2. **Commandes, Flags & Contextes Multimodaux** — Slash commands, CLI flags, `@` références, raccourcis clavier
3. **Configuration & Personnalisation** — settings.json, GEMINI.md, .geminiignore, MCP Servers, commandes TOML
4. **Outils Intégrés** — Système de fichiers, Web, Mémoire & Shell
5. **Fonctionnalités Avancées** — Sandbox, Search Grounding, Checkpointing, Headless, Extensions, VS Code, Model Routing, Git Worktrees
6. **Conseils d'Utilisation Pro** — Chain of Thought, Few-Shot, Prompts mauvais vs bons, gestion de sessions
7. **Idées Réalistes & Cas d'Usage** — 8 projets concrets avec prompts
8. **Workflow complet type** — De l'init à la sauvegarde de session
9. **Cheat Sheet Express** — Récapitulatif one-page

---

## 🔥 Exemples de commandes

### Lancer Gemini CLI

```bash
# Mode interactif (REPL)
gemini

# Mode non-interactif — une seule réponse
gemini -p "Explique le pattern MVC en 3 phrases"

# Piping — analyser un fichier
cat README.md | gemini -p "Résume ce fichier"

# Mode sandbox sécurisé
gemini --sandbox -p "Analyse ces logs d'erreur"
```

### Slash Commands essentielles

```bash
/compress          # Résumer le contexte pour économiser des tokens
/stats             # Voir la consommation de tokens
/chat save auth    # Sauvegarder la session
/chat resume auth  # Reprendre une session
/restore           # Restaurer un checkpoint
/init              # Générer un GEMINI.md
/mcp               # Lister les serveurs MCP
```

### @ Contextes multimodaux

```bash
@./src/auth.ts              # Référencer un fichier
@./maquette-dashboard.png   # Image → génération de code
@./meeting-notes.mp3        # Audio → transcription & résumé
@./demo-app.mp4             # Vidéo → analyse visuelle
@./src/                     # Tout un répertoire (avec .geminiignore)
```

---

## 🛠️ Technologies couvertes

- **Gemini CLI** — Agent IA open-source de Google pour le terminal
- **Google AI Studio** — Génération de clés API
- **MCP (Model Context Protocol)** — Extension protocol pour serveurs d'outils personnalisés
- **Sandbox Docker/Podman** — Exécution sécurisée de code
- **Checkpointing Git** — Snapshots automatiques avant modifications
- **VS Code Integration** — Connexion IDE pour contexte enrichi
- **Commandes TOML** — Slash commands personnalisées

---

## 🤝 Contribuer

Les contributions sont les bienvenues ! Voici comment participer :

1. **Fork** le dépôt
2. Créez une **branche feature** : `git checkout -b feature/ma-contribution`
3. **Commitez** vos changements : `git commit -m "Ajout de ..."`
4. **Poussez** sur votre fork : `git push origin feature/ma-contribution`
5. Ouvrez une **Pull Request**

### Idées de contribution

- 🌍 Traduction en anglais, espagnol, etc.
- 📸 Captures d'écran du guide en action
- 🆕 Nouveaux cas d'usage réalistes
- 🔧 Corrections ou mises à jour suite aux évolutions de Gemini CLI
- 🎨 Améliorations du design CSS

---

## 📜 Licence

Ce projet est sous licence **MIT** — voir le fichier [LICENSE](./LICENSE) pour plus de détails.

Le guide lui-même est fourni à titre informatif. Gemini CLI est un produit open-source de Google — [Dépôt officiel](https://github.com/google-gemini/gemini-cli).

---

## 🔗 Liens utiles

| Ressource | Lien |
|---|---|
| Dépôt officiel Gemini CLI | [github.com/google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli) |
| Documentation Google AI | [ai.google.dev](https://ai.google.dev/) |
| Google AI Studio (clés API) | [aistudio.google.com](https://aistudio.google.com/app/apikey) |
| Spécification MCP | [modelcontextprotocol.io](https://modelcontextprotocol.io/) |
| npm @google/gemini-cli | [npmjs.com/package/@google/gemini-cli](https://www.npmjs.com/package/@google/gemini-cli) |

---

<div align="center">

**Fait avec ❤️ pour la communauté francophone Gemini CLI**

Si ce guide vous est utile, n'hésitez pas à laisser une ⭐ sur le dépôt !

</div>

---

## 🇬🇧 English Version

> **A comprehensive, single-file HTML guide for mastering Google's Gemini CLI** — the open-source AI agent for your terminal.

This guide covers everything from installation and authentication to advanced features like MCP servers, sandbox code execution, checkpointing, and 8 realistic use cases. It's written in French and features a modern dark-mode design with floating navigation, copy buttons, and scroll animations.

**Quick start:** Just open `guide-gemini-cli.html` in any browser. No build step, no dependencies — it just works.

Key sections:
- **Installation & Auth** — npm, npx, secure API key management
- **Commands & Flags** — All slash commands, CLI flags, multimodal `@` references
- **Configuration** — settings.json (3 levels), GEMINI.md (hierarchical), .geminiignore, TOML custom commands
- **MCP Protocol** — Model Context Protocol server configuration, `gemini mcp add`
- **Built-in Tools** — File system, web search, memory, shell execution
- **Advanced Features** — Code Interpreter/Sandbox, Google Search Grounding, Checkpointing, Headless mode, VS Code integration
- **Pro Tips** — Chain of Thought, Few-Shot Prompting, good vs bad prompts
- **8 Realistic Use Cases** — UI from mockup, security audit, framework migration, auto-documentation, and more
- **Cheat Sheet** — Quick reference table

Contributions welcome — especially translations and updates as Gemini CLI evolves!
