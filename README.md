# My Dotfiles Manager

This script provides a simple way to manage your dotfiles (configuration files) using either [stow](https://www.gnu.org/software/stow/) or [chezmoi](https://chezmoi.io/). It allows you to easily switch between different dotfile configurations using a menu-driven interface ([rofi](https://github.com/davdes/rofi) or [dmenu](https://tools.suckless.org/dmenu/)).

## Prerequisites

- Git
- Either `stow` or `chezmoi` installed
- Either `rofi` or `dmenu` installed (for the selection menu)

## Installation

1. **Clone this repository:**
   ```
   git clone https://github.com/yourusername/your-dotfiles-manager.git
   cd your-dotfiles-manager 
   ```
2. **Make the script executable:**
   ```
   chmod +x dotfiles-manager.sh
   ```

## Configuration

1. **Edit the `dotfiles-manager.sh` script:**
   - **`DOTFILES_REPO`:** Replace the placeholder with the URL of your dotfiles repository. 
   - **`CONFIG_OPTIONS`:**  List the names of your configuration branches/tags in your dotfiles repository (e.g., "work", "home", "gaming").
   - **`DOTFILE_MANAGER`:** Choose either "stow" or "chezmoi".
   - **`MENU_PROGRAM`:** Choose either "rofi" or "dmenu".

## Usage

1. **Run the script:**
   ```
   ./dotfiles-manager.sh 
   ```
2. **Choose a configuration:**
   - A menu will appear (using `rofi` or `dmenu`) with the options listed in `CONFIG_OPTIONS`.
   - Select the configuration you want to apply. 

## How it Works

- The script clones your dotfiles repository to a temporary directory.
- It then uses the selected dotfile manager (`stow` or `chezmoi`) to manage the symlinks/files from the temporary directory to their correct locations in your home directory.
- **Important:** The script overwrites specific config files - make sure to adjust this behavior in the script if needed!

## Customization

- **Add more configurations:**  Add more branch/tag names to the `CONFIG_OPTIONS` array in the script.
- **Change menu appearance:**  Explore the options for `rofi` or `dmenu` to customize the menu appearance. 

## Warnings

- **Backup Your Dotfiles:** Before running the script, back up your existing dotfiles to avoid any data loss. 
- **Review Configuration Files:** Be cautious about overwriting configuration files. Ensure that your dotfiles repository is set up correctly and doesn't contain sensitive information.

## Contributing

Contributions are welcome! Feel free to open issues or pull requests. 

## License

[HPOG License](LICENSE)
