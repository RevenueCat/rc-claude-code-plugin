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

### Paywall Builder Agent

Create and configure offerings, packages, and paywalls for optimal conversion.

**Trigger phrases:**
- "Create a paywall for my app"
- "Set up subscription offerings"
- "I want to A/B test pricing"

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

This plugin uses the RevenueCat MCP server which provides these tools:

| Tool | Description |
|------|-------------|
| `mcp_RC_get_project` | Get project details |
| `mcp_RC_create_project` | Create a new project |
| `mcp_RC_list_apps` | List all apps |
| `mcp_RC_create_app` | Create an app |
| `mcp_RC_list_products` | List all products |
| `mcp_RC_create_product` | Create a product |
| `mcp_RC_list_entitlements` | List entitlements |
| `mcp_RC_create_entitlement` | Create an entitlement |
| `mcp_RC_attach_products_to_entitlement` | Attach products to entitlement |
| `mcp_RC_list_offerings` | List offerings |
| `mcp_RC_create_offering` | Create an offering |
| `mcp_RC_list_packages` | List packages in an offering |
| `mcp_RC_create_package` | Create a package |
| `mcp_RC_attach_products_to_package` | Attach products to package |
| `mcp_RC_create_webhook_integration` | Create webhook |
| `mcp_RC_list_public_api_keys` | Get public API keys |

See the [full API documentation](https://www.revenuecat.com/docs/api-v2) for details.

## Support

- [RevenueCat Documentation](https://www.revenuecat.com/docs)
- [MCP Server Documentation](https://www.revenuecat.com/docs/tools/mcp/overview)
- [Community Forum](https://community.revenuecat.com/)
- [GitHub Issues](https://github.com/RevenueCat/rc-claude-code-plugin/issues)

## License

MIT License - see the main repository for details.
