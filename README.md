# OpenCode Configuration Example

This repository provides a basic example of OpenCode configuration that you can use as a reference and customize according to your needs.

## What is opencode.json?

The `opencode.json` file is a configuration file for OpenCode that defines project settings, build configurations, testing preferences, and more.

## Configuration Structure

The example configuration includes:

- **version**: Configuration version
- **project**: Basic project information (name, description, type)
- **settings**: Editor and development settings
  - Auto-save functionality
  - Format on save
  - Linting rules
  - Code style preferences (indentation, line endings)
- **build**: Build configuration (source and output directories)
- **testing**: Testing framework and coverage settings
- **dependencies**: Dependency management preferences
- **extensions**: Recommended extensions for the project
- **paths**: Include and exclude patterns for project files

## Usage

1. Copy the `opencode.json` file to your project root
2. Modify the configuration values according to your project needs
3. OpenCode will automatically detect and use the configuration

## Customization

Feel free to adjust any settings in the `opencode.json` file:

- Change `indentSize` to match your preferred indentation (2 or 4 spaces, tabs)
- Modify `coverageThreshold` for your testing requirements
- Add your preferred extensions to the `recommended` array
- Update `includes` and `excludes` patterns based on your project structure

## License

MIT License - see [LICENSE](LICENSE) file for details