# Claude Code EZ Switch

A user-friendly Windows desktop application that allows you to easily switch between different Claude API configurations, including Z.ai, Anthropic Claude, and custom endpoints.

**⚠️ Important Note**: This tool has only been tested with the CLI version of Claude Code and is not guaranteed to work with the VS Code extension version of Claude Code.

![Claude Code EZ Switch](https://img.shields.io/badge/Platform-Windows-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.7%2B-yellow?style=flat-square)

## 🚀 Features

- **Easy Configuration Switching**: Seamlessly switch between Z.ai, Anthropic Claude, and custom API endpoints
- **Persistent Storage**: Securely saves your API keys locally for convenience
- **Real-time Status Display**: Shows your current configuration at a glance
- **Modern Dark Theme**: Clean, professional interface with dark mode styling
- **Password Visibility Toggle**: Show/hide API keys for security
- **Automatic Detection**: Detects and pre-fills existing environment variables
- **Threading Support**: Non-blocking UI with loading indicators

## 📋 System Requirements

- **Operating System**: Windows 10 or later
- **Python**: 3.7 or higher
- **Tested With**: Claude Code CLI version only
- **Not Tested**: VS Code extension version of Claude Code
- **Dependencies**: tkinter (included with Python), subprocess, os, sys, threading, json, pathlib

## 🛠️ Installation

1. **Clone or download this repository**:
   ```bash
   git clone https://github.com/techcow2/claude-code-ez-switch.git
   cd claude-code-ez-switch
   ```

2. **Run the application**:
   ```bash
   python ezswitch.py
   ```

No additional packages need to be installed - all dependencies are included with standard Python installations!

## 🎯 How to Use

### 1. Launch the Application
Simply run `ezswitch.py` to open the configuration manager.

### 2. Choose Your Configuration

#### **Z.ai Configuration**
- Select "Z.ai" radio button
- Enter your Z.ai API key
- Click "Apply Configuration"

#### **Anthropic Claude Configuration**
- Select "Anthropic" radio button
- Choose between:
  - **Subscription Mode**: Use your Claude Pro/Team/Enterprise subscription
  - **API Key Mode**: Enter your Claude API key
- Click "Apply Configuration"

#### **Custom Configuration**
- Select "Custom" radio button
- Enter your custom base URL (e.g., `https://your-api-endpoint.com`)
- Enter your custom API key
- Click "Apply Configuration"

### 3. Apply Changes
After clicking "Apply Configuration":
- The application will set the necessary environment variables
- **🔴 CRITICAL**: You must close **ALL** applications running Claude Code, including:
  - VS Code (if running Claude Code in the VS Code terminal)
  - PowerShell terminals
  - Command Prompt terminals
  - Any other applications using Claude Code
- Then reopen these applications for changes to take effect
- Environment variables are only read when applications first start

### 4. Special Login Requirements
**When switching to Anthropic configuration from another configuration:**
- After reopening Claude Code CLI, you must log back into your Anthropic account
- Run the command: `/login`
- This is required because switching from other endpoints clears your authentication session

### 5. Verify Configuration
Use the "Refresh" button to check your current configuration status at any time.

## 🔧 Configuration Details

The application manages the following Windows user environment variables:

- `ANTHROPIC_AUTH_TOKEN`: Your API authentication token
- `ANTHROPIC_BASE_URL`: The API base URL (if applicable)

### Configuration Examples:

**Z.ai**:
- `ANTHROPIC_AUTH_TOKEN`: Your Z.ai API key
- `ANTHROPIC_BASE_URL`: `https://api.z.ai/api/anthropic`

**Claude API**:
- `ANTHROPIC_AUTH_TOKEN`: Your Claude API key
- `ANTHROPIC_BASE_URL`: Not set (uses default)

**Custom**:
- `ANTHROPIC_AUTH_TOKEN`: Your custom API key
- `ANTHROPIC_BASE_URL`: Your custom endpoint URL

## 🔒 Security Features

- **Local Storage**: API keys are stored locally in `~/.claude_code_ez_switch_config.json`
- **Password Masking**: API keys are hidden by default with asterisks
- **Secure Environment Variables**: Uses Windows user-level environment variables
- **No Cloud Storage**: No data is sent to external servers

## 🎨 Interface Features

- **Dark Theme**: Easy on the eyes with professional dark color scheme
- **Status Display**: Real-time configuration status with masked API keys
- **Loading Indicators**: Visual feedback during configuration changes
- **Hover Effects**: Interactive buttons with smooth transitions
- **Responsive Layout**: Clean, organized interface with proper spacing

## 🐛 Troubleshooting

### Common Issues:

1. **"This application is designed for Windows only"**
   - This app only works on Windows due to PowerShell environment variable management

2. **Configuration not taking effect**
   - **CRITICAL**: Make sure you have closed ALL applications using Claude Code (VS Code, PowerShell, Command Prompt, etc.) before reopening them
   - Environment variables are only loaded when applications start, not dynamically
   - Check that your application reads user-level environment variables

3. **Authentication issues when switching to Anthropic**
   - After switching to Anthropic configuration, you must run `claude code /login` in the CLI
   - This is required because switching from other endpoints clears your authentication session
   - Make sure you're logged into the correct Anthropic account

4. **API keys not saving**
   - Ensure the application has write permissions to your user home directory
   - Check for the config file at `%USERPROFILE%\.claude_code_ez_switch_config.json`

5. **PowerShell command failures**
   - Run the application as Administrator if you encounter permission issues
   - Ensure PowerShell execution policy allows running scripts

## 📝 Development

### Project Structure:
```
claude-code-ez-switch/
├── ezswitch.py              # Main application file
├── README.md                # This documentation
└── .git/                    # Git repository
```

### Key Components:

- **ClaudeConfigSwitcher**: Main application class
- **Configuration Frames**: Dynamic UI for different API configurations
- **Environment Management**: PowerShell integration for Windows environment variables
- **Persistent Storage**: JSON-based configuration storage

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

### Development Setup:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly on Windows
5. Submit a pull request

## 📄 License

This project is open source under the MIT License. See the [LICENSE](LICENSE) file for details.