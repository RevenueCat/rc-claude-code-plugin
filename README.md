# RevenueCat Claude Code Plugin

Configure RevenueCat projects, products, entitlements, and offerings directly from Claude Code. Manage your in-app purchase backend without leaving your IDE.

## Installation

### Option 1: Direct URL (Recommended)

In Claude Code, run:

```
/plugin add https://github.com/RevenueCat/rc-claude-code-plugin
```

### Option 2: Manual Installation

1. Clone this repository
2. In Claude Code, run:
   ```
   /plugin add /path/to/rc-claude-code-plugin
   ```

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
