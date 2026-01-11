# OpenCode Configuration Example

This repository provides a practical example of OpenCode configuration that demonstrates real-world usage patterns for AI-assisted development workflows.

## What is opencode.json?

The `opencode.json` file is a configuration file for OpenCode that defines AI provider settings, model preferences, permissions, file watching patterns, and custom instructions.

## Configuration Structure

The example configuration includes:

- **$schema**: JSON schema reference for IDE validation and autocomplete
- **enabled_providers**: List of active AI providers (e.g., "github-copilot")
- **provider**: Provider-specific configuration
  - Timeout settings for API calls
  - Authentication and connection options
- **model**: Default AI model for coding tasks (e.g., "github-copilot/claude-sonnet-4.5")
- **small_model**: Lightweight model for quick tasks (e.g., "github-copilot/gpt-5-mini")
- **permission**: Safety controls for file operations
  - `edit`: Permission for editing files ("ask", "allow", "deny")
  - `write`: Permission for creating files
  - `bash`: Permission for running shell commands
- **watcher**: File watching configuration to reduce noise
  - Ignore patterns for build outputs, dependencies, and temporary files
- **mcp**: Model Context Protocol integrations
  - External tool and service integrations (e.g., AWS documentation)
- **instructions**: Custom instruction files for domain-specific guidance
  - Architecture and design patterns
  - Technology-specific best practices
  - Security and quality standards

## Usage

1. Copy the `opencode.json` file to your project root or `~/.config/opencode/`
2. Modify the configuration values according to your needs
3. Update the `instructions` paths to point to your instruction files (or remove if not using)
4. OpenCode will automatically detect and use the configuration

## Customization

Feel free to adjust any settings in the `opencode.json` file:

- Change `model` and `small_model` to your preferred AI models
- Adjust `permission` settings based on your trust level and workflow
- Add or remove patterns in `watcher.ignore` for your project structure
- Configure `mcp` integrations for additional tools and services
- Update `instructions` array to reference your custom instruction files

## Key Features

- **Predictable AI behavior**: Single provider configuration ensures consistent responses
- **Safety first**: Ask-before-action permissions prevent unintended changes
- **Performance optimization**: File watcher ignores reduce context noise
- **Extensibility**: MCP integrations enable custom tool connections
- **Domain expertise**: Instruction files provide technology-specific guidance

## License

MIT License - see [LICENSE](LICENSE) file for details