# Claude Code EZ Switch

A Windows desktop application to easily switch between Claude Code API configurations (Z.ai, Anthropic, custom endpoints).

![Claude Code EZ Switch](https://img.shields.io/badge/Platform-Windows-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.7%2B-yellow?style=flat-square)

## Features

- Switch between Z.ai, Anthropic Claude, and custom API endpoints  
- Securely saves API keys locally  
- Shows your current configuration  
- Auto-detects existing environment variables  

## Requirements

- Python 3.7+  
- Windows 10 or above  
- Claude Code CLI  

## Installation

```
git clone https://github.com/techcow2/claude-code-ez-switch.git
cd claude-code-ez-switch
python ezswitch.py
```

## Quick Start

1. Run `python ezswitch.py`  
2. Select your configuration (Z.ai, Anthropic, or Custom) and enter your API key/URL  
3. Click **Apply Configuration**  
4. Close and reopen all Claude Code applications (VS Code, terminals, etc.) for changes to take effect  
5. If switching to Anthropic, run `/login` in the CLI to re-authenticate  

## How It Works

The app sets these Windows environment variables:  

- `ANTHROPIC_AUTH_TOKEN`: Your API key  
- `ANTHROPIC_BASE_URL`: Your API endpoint (if custom)  

Both Claude Code CLI and the VS Code extension read these variables on startup.  

## Troubleshooting

- **Changes not working?** Close all Claude Code apps and reopen them. Variables only load on startup.  
- **Permission denied?** Run the app as Administrator.  
- **Anthropic login failed?** Run `/login` in the CLI after switching to Anthropic.  

## License

[MIT License](https://github.com/techcow2/claude-code-ez-switch/blob/master/LICENSE)
```
