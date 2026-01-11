# opencode-configuration-example

This repository contains an example OpenCode configuration for a .NET engineer and cloud solution architect role, focused on production workloads, distributed systems, and long-lived adaptable systems.

## Structure

- **`opencode.json`**: Main configuration file that defines the OpenCode setup
- **`instructions/`**: Directory containing modular instruction files for different aspects of development

## Instruction Files

The configuration includes the following instruction modules:

1. **00-role-and-mindset.md** - Core role definition and mindset
2. **10-dotnet-core.md** - .NET Core development guidelines
3. **20-web-apis.md** - ASP.NET Core Web API best practices
4. **30-distributed-systems.md** - Distributed systems design principles
5. **40-messaging-events.md** - Messaging and event-driven architecture
6. **50-data-persistence.md** - Data storage and EF Core guidelines
7. **60-cloud-platforms.md** - Azure and AWS cloud platform considerations
8. **70-containers-kubernetes.md** - Container and Kubernetes best practices
9. **80-observability-operations.md** - Observability and operational excellence
10. **90-testing-quality.md** - Testing strategies and quality assurance
11. **95-security.md** - Security principles and practices
12. **99-evolution-documentation.md** - Evolution and documentation strategies
13. **anti-patterns.md** - Common anti-patterns to avoid with explanations

## Configuration Highlights

- **Provider**: GitHub Copilot with Claude Sonnet 4.5 as the main model
- **Small Model**: GPT-5 Mini for lightweight tasks
- **Permissions**: Ask-before-edit mode for safety
- **MCP Integration**: AWS documentation server enabled
- **Watcher**: Ignores build artifacts and dependencies

## Usage

This configuration is designed to be placed in your OpenCode configuration directory (typically `~/.config/opencode/`) and customized as needed for your specific development environment and team practices.