# rust-faf-cli

[![Downloads](https://img.shields.io/github/downloads/Wolfe-Jam/rust-faf-cli/total)](https://github.com/Wolfe-Jam/rust-faf-cli/releases)

**FAF Compiler** — AI-Readiness scoring engine for [.faf](https://faf.one) files. Rust-native CLI.

Score any project's AI context quality. See exactly why. Fix it automatically.

## Install

**Homebrew (macOS/Linux):**
```bash
brew install Wolfe-Jam/faf/rust-faf-cli
```

**Direct download:**
```bash
# macOS ARM (Apple Silicon)
curl -L https://github.com/Wolfe-Jam/rust-faf-cli/releases/latest/download/faf-1.1.0-aarch64-apple-darwin.tar.gz | tar xz
sudo mv faf /usr/local/bin/

# macOS Intel
curl -L https://github.com/Wolfe-Jam/rust-faf-cli/releases/latest/download/faf-1.1.0-x86_64-apple-darwin.tar.gz | tar xz
sudo mv faf /usr/local/bin/

# Linux x86_64
curl -L https://github.com/Wolfe-Jam/rust-faf-cli/releases/latest/download/faf-1.1.0-x86_64-unknown-linux-gnu.tar.gz | tar xz
sudo mv faf /usr/local/bin/
```

**Windows:** Download `faf-1.1.0-x86_64-pc-windows-msvc.zip` from [Releases](https://github.com/Wolfe-Jam/rust-faf-cli/releases).

## What It Does

```
$ faf status

Mission Status Report
==================================================

  Project:  my-app
  Score:    73%
  Tier:     GO! Ready

Glass Hood Analysis
--------------------------------------------------
  Completeness   [===============     ]  75.0% x 40% =  30.0
  Clarity        [==============      ]  70.0% x 35% =  24.5
  Structure      [================    ]  80.0% x 15% =  12.0
  Metadata       [=============       ]  65.0% x 10% =   6.5
--------------------------------------------------
  TOTAL                                          73.0%

GO! 73 - Ready  |  ONE thing to improve:
  -> [DO] Add key_files to project.faf (3 items minimum)
  -> Projected: 73% -> 82%
```

Every score is transparent. Glass Hood shows exactly how it's calculated — weights, categories, projections. Nothing hidden.

## Commands

| Command | What it does |
|---------|-------------|
| `faf init <name>` | Create project.faf + context files |
| `faf status` | Score + tier + top suggestion |
| `faf status --verbose` | Glass Hood deep-dive |
| `faf status --card` | Generate score-card.svg |
| `faf status --json` | Machine-readable JSON |
| `faf sync` | Sync to GROK.md, CLAUDE.md, GEMINI.md |
| `faf sync --claude` | Sync CLAUDE.md only |
| `faf gold` | Gap analysis to reach 100% |
| `faf compile` | Compile .faf to .fafb binary (288x faster) |
| `faf bench` | Race benchmark: FAF vs FAFB |
| `faf embed grok` | Embeddable context header |
| `faf completions zsh` | Shell completions |

## Scoring

Four categories, weighted by impact on AI comprehension:

| Category | Weight | What it measures |
|----------|--------|-----------------|
| Completeness | 40% | Are all context slots filled? |
| Clarity | 35% | Is the context unambiguous? |
| Structure | 15% | Is it well-organized? |
| Metadata | 10% | Version, timestamps, DNA tracking |

Language bonuses: Rust +15, Go +10, TypeScript +5.

## Tier System

| Score | Tier | Status |
|-------|------|--------|
| 100%+ | Rocket | Mission-Ready |
| 99% | Gold | Almost there |
| 95% | Silver | Top tier |
| 85% | Bronze | Production ready |
| 70% | GO! | Solid foundation |
| 55% | Caution | Needs improvement |
| <55% | Stop | Major work needed |

## FAFb Binary Format

Compile `.faf` (YAML) to `.fafb` (binary) for O(1) section lookup. 288x faster parsing. Priority truncation fits any context window.

IANA registered: `application/vnd.faf+yaml`

## Links

- [faf.one](https://faf.one) — Main site
- [faf-rust-sdk](https://crates.io/crates/faf-rust-sdk) — Rust SDK (MIT, crates.io)
- [faf-cli](https://www.npmjs.com/package/faf-cli) — TypeScript CLI (npm)
- [claude-faf-mcp](https://www.npmjs.com/package/claude-faf-mcp) — Claude MCP server
- [All packages](https://faf.one/links) — Full ecosystem directory

## License

Proprietary. See [LICENSE](LICENSE).

---

**team@faf.one** | [faf.one](https://faf.one)
