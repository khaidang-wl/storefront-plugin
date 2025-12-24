# Example Plugin for Claude Code

A simple example plugin demonstrating the key features of Claude Code's plugin system. This plugin includes slash commands, a custom agent, and hooks to enhance your coding workflow.

## Features

### Slash Commands

This plugin provides three useful slash commands:

- **`/example-plugin:greet [name]`** - Get a friendly greeting, optionally personalized with your name
- **`/example-plugin:analyze [file]`** - Analyze code for quality, performance, security, and best practices
- **`/example-plugin:explain [file]`** - Get a clear explanation of what code does and how it works

### Custom Agent

- **`code-reviewer`** - A specialized agent focused on thorough code reviews covering correctness, security, performance, best practices, maintainability, and testing

### Hooks

The plugin includes helpful hooks that:

- **Post-Edit Hook**: After you modify files, reminds you to consider updating tests and documentation
- **Pre-Submit Hook**: Gentle reminders about best practices before each interaction

## Installation

### Option 1: Using --plugin-dir (for testing)

Test the plugin locally without installing:

```bash
claude --plugin-dir ./example-plugin
```

### Option 2: Install via Marketplace

If this plugin is published in a marketplace:

```bash
/plugin marketplace add <marketplace-source>
/plugin install example-plugin@<marketplace-name>
```

### Option 3: Local Installation

Copy the plugin to your Claude Code plugins directory, or create a custom marketplace for your team.

## Usage

### Using Slash Commands

```bash
# Get a personalized greeting
/example-plugin:greet Alice

# Analyze the current file or selection
/example-plugin:analyze

# Analyze a specific file
/example-plugin:analyze src/utils/helper.ts

# Explain selected code or a file
/example-plugin:explain src/components/Button.tsx
```

### Using the Code Reviewer Agent

Launch the code-reviewer agent for a thorough review:

```bash
/agents
# Select "code-reviewer" from the list
```

Or reference it in your conversation:
```
Please review this pull request using the code-reviewer agent
```

### Hooks in Action

The hooks work automatically:

- After you edit a file, you'll get a reminder to update tests and docs
- Before each prompt, you'll see best practice reminders

## Plugin Structure

```
example-plugin/
├── .claude-plugin/
│   └── plugin.json          # Plugin manifest with metadata
├── commands/
│   ├── greet.md            # Greeting slash command
│   ├── analyze.md          # Code analysis command
│   └── explain.md          # Code explanation command
├── agents/
│   └── code-reviewer.md    # Code review specialist agent
├── hooks/
│   └── hooks.json          # Event hooks configuration
└── README.md               # This file
```

## Customization

Feel free to modify this plugin to suit your needs:

1. **Edit commands**: Modify the `.md` files in `commands/` to change command behavior
2. **Customize the agent**: Update `agents/code-reviewer.md` to adjust the review focus
3. **Adjust hooks**: Edit `hooks/hooks.json` to change when and how reminders appear
4. **Update metadata**: Change `plugin.json` to reflect your customizations

## Development

To develop this plugin further:

1. Make changes to the plugin files
2. Test with `claude --plugin-dir ./example-plugin`
3. Restart Claude Code to pick up changes
4. Use `/help` to verify your commands appear
5. Test each component thoroughly

## Learn More

- [Claude Code Plugin Documentation](https://code.claude.com/docs/en/plugins.md)
- [Plugin Marketplaces](https://code.claude.com/docs/en/plugin-marketplaces.md)
- [Slash Commands Guide](https://code.claude.com/docs/en/slash-commands)
- [Hooks Documentation](https://code.claude.com/docs/en/hooks)
- [Agent Development](https://code.claude.com/docs/en/sub-agents)

## License

MIT License - feel free to use, modify, and distribute this example plugin.

## Contributing

This is an example plugin for learning purposes. Feel free to fork it and create your own plugins based on this structure!
