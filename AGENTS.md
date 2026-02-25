# ZMK Dactyl Manuform 6x7 Keyboard Configuration

This is a ZMK keyboard firmware configuration for a Dactyl Manuform 6x7 split keyboard using nice_nano_v2 controllers.

## Build Commands
- **Build firmware**: GitHub Actions automatically builds on push/PR using `.github/workflows/build.yml`
- **Local build**: Not configured - relies on ZMK's remote build system
- **No test/lint commands** - ZMK firmware uses device tree syntax validation

## Code Style Guidelines
- **File types**: `.dtsi`, `.overlay`, `.keymap`, `.conf` (Device Tree and ZMK config files)
- **Comments**: Use `//` for single line, `/* */` for multi-line in device tree files
- **Indentation**: 4 spaces consistently used throughout codebase
- **Layer definitions**: Use `#define` constants (DEFAULT 0, LOWER 1, RAISE 2, ADJUST 3)
- **Key bindings**: Align in columns with spacing for readability, group left/right sides
- **Includes**: Place at top with `#include <path>` format, group related includes together
- **GPIO config**: Use descriptive flags like `GPIO_ACTIVE_HIGH | GPIO_PULL_DOWN`
- **Split config**: Left/right shields defined in separate overlay files
- **Naming**: Use lowercase with underscores for files, UPPERCASE for layer constants

## Configuration Files
- `build.yaml`: Defines build matrix for GitHub Actions (board/shield combinations)
- `config/dactyl.keymap`: Main keymap with custom vim-like bindings and mouse support
- `boards/shields/dactyl/`: Shield definition files (dtsi, overlays, Kconfig)
- `config/west.yml`: ZMK framework manifest pointing to v0.2

## Key Features
- 6x7 matrix with 5-way switch support and custom macros (tmux_n1-4, vim_write, etc.)