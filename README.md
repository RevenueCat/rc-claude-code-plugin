# RevenueCat Claude Code Plugin

Configure RevenueCat projects, products, entitlements, and offerings directly from Claude Code. Manage your in-app purchase backend without leaving your IDE.

## Installation

### Prerequisites

- Claude Code version 1.0.33 or later (run `claude --version` to check)

### Method 1: Using `--plugin-dir` Flag (Quick Start)

1. Clone this repository:

   ```bash
   git clone https://github.com/RevenueCat/rc-claude-code-plugin.git
   ```

2. Start Claude Code with the plugin directory:

   ```bash
   claude --plugin-dir /path/to/rc-claude-code-plugin
   ```

   You can specify multiple plugins by repeating the flag:

   ```bash
   claude --plugin-dir /path/to/rc-claude-code-plugin --plugin-dir /path/to/other-plugin
   ```

### Method 2: Permanent Installation via Settings (Recommended)

1. Clone this repository:

   ```bash
   git clone https://github.com/RevenueCat/rc-claude-code-plugin.git
   ```

2. Add the plugin to your Claude Code settings file:

   **User-level** (available across all projects):
   Edit `~/.claude/settings.json`:

   ```json
   {
     "plugins": [
       "/absolute/path/to/rc-claude-code-plugin"
     ]
   }
   ```

   **Project-level** (shared with your team via git):
   Edit `.claude/settings.json` in your project root:

   ```json
   {
     "plugins": [
       "/absolute/path/to/rc-claude-code-plugin"
     ]
   }
   ```

   **Local project-level** (personal, not shared):
   Edit `.claude/settings.local.json` in your project root (add to `.gitignore`):

   ```json
   {
     "plugins": [
       "/absolute/path/to/rc-claude-code-plugin"
     ]
   }
   ```

3. Restart Claude Code or reload the plugin:

   ```bash
   claude
   ```

### Verify Installation

Once installed, verify the plugin is loaded by checking for the `/rc:` commands:

- `/rc:status` - View project status
- `/rc:apikey` - Get API keys
- `/rc:create-app` - Create a new app
- `/rc:create-product` - Create a new product

You can also use natural language to trigger agents:

- "Set up RevenueCat for my app"
- "Debug my RevenueCat configuration"

### Future: Installing from Claude Plugin Marketplace

This plugin will soon be available via the official Claude Code plugin marketplace for easier installation. Stay tuned!

## Authentication

The plugin requires authentication with your RevenueCat account via OAuth.

When you first use a RevenueCat tool, you'll be prompted to authenticate via OAuth in your browser. This grants Claude Code access based on your RevenueCat account permissions and allows access to all your projects.

## Available Skills (Slash Commands)

| Command | Description |
|---------|-------------|
| `/rc:status` | Get a quick overview of your RevenueCat project |
| `/rc:apikey` | Retrieve public API keys for SDK initialization |
| `/rc:create-product` | Guided product creation wizard |
| `/rc:create-app` | Step-by-step guide for setting up an iOS or Android app |

## Available Agents

### Project Bootstrap Agent

Complete project setup from scratch. Creates apps, products, entitlements, offerings, and packages in the correct order.

**Trigger phrases:**
- "Set up RevenueCat for my new app"
- "Help me create a subscription backend"
- "Bootstrap my RevenueCat project"

### Troubleshooting Agent

Diagnose and fix common integration issues. Systematically checks your configuration for problems.

**Trigger phrases:**
- "My purchases aren't working"
- "Debug my RevenueCat setup"
- "Users aren't getting premium access"

## Example Workflows

### New App Setup

```
You: Set up RevenueCat for my fitness app

Claude: I'll help you set up RevenueCat. What platforms are you building for?

You: iOS and Android

Claude: Creating your iOS app... [creates app]
        Creating your Android app... [creates app]
        What subscription tiers do you want? (e.g., monthly, annual)

You: Monthly at $9.99 and annual at $79.99

Claude: [Creates products, entitlements, offering, packages]
        
        Setup complete! Here are your API keys:
        iOS: appl_xxxxx
        Android: goog_xxxxx
```

### Quick Product Check

```
You: /rc:status

Claude: RevenueCat Project Status
        ============================
        Project: Fitness App (proj123)
        
        Apps: 2 (iOS, Android)
        Products: 4
        Entitlements: 2
        Offerings: 1
        
        ✅ Configuration looks healthy!
```

### Debug an Issue

```
You: Users are purchasing but not getting premium access

Claude: I'll diagnose this. Let me check your configuration...
        
        [Checks products, entitlements, attachments]
        
        Found 1 issue:
        ⚠️ Product "annual_premium" is not attached to any entitlement
        
        Would you like me to fix this?
```

## MCP Tools Reference

This plugin uses the RevenueCat MCP server which provides tools for common configuration actions.

See the [full MCP tools reference](https://www.revenuecat.com/docs/tools/mcp/tools-reference) for complete details on all available tools.

## Support

- [RevenueCat Documentation](https://www.revenuecat.com/docs)
- [MCP Server Documentation](https://www.revenuecat.com/docs/tools/mcp/overview)
- [Community Forum](https://community.revenuecat.com/)
- [GitHub Issues](https://github.com/RevenueCat/rc-claude-code-plugin/issues)

## License

MIT License - see the main repository for details.
