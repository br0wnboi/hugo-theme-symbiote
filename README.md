# Hugo Theme Symbiote

A dark, minimalistic, terminal-inspired Hugo theme built for security researchers and hackers.

## Features
- Fully responsive terminal UI
- Hugo Pipes integration for heavily optimized CSS
- Robust internationalization (i18n) support
- Dynamic, extensible color schemes

## Installation

Inside your Hugo project, add the theme as a submodule:
```bash
git submodule add https://github.com/br0wnboi/hugo-theme-symbiote.git themes/hugo-theme-symbiote
```

Then, add this to your `hugo.toml`:
```toml
theme = "hugo-theme-symbiote"
```

## Creating Custom Color Schemes

This theme allows you to create custom color schemes that automatically hook into the Javascript theme-switcher.

1. Create a `static/css/custom.css` (or `assets/css/custom.css`) in your project.
2. Define the strict 9-variable CSS API under a `:root[data-theme="your-theme-name"]` selector:
```css
:root[data-theme="your-theme-name"] {
    --bg:          #000000;
    --bg-surface:  #111111;
    --bg-elevated: #222222;
    --text:        #dddddd;
    --text-dim:    #888888;
    --text-bright: #ffffff;
    --accent:      #ff0000;
    --accent-dim:  #aa0000;
    --border:      #333333;
}
```
3. Update your `hugo.toml` to tell the theme-switcher about it:
```toml
[params]
  themes = ["your-theme-name", "venom", "charcoal"]
```

## Restricting or Removing Themes

If you only want specific themes to show up on your website (e.g., you only want to cycle between `amoled` and `venom`), you do not need to delete any CSS. 

Simply restrict the `themes` array in your `hugo.toml`:
```toml
[params]
  themes = ["amoled", "venom"]
```
The Javascript toggle will instantly respect this list and ignore all other built-in themes.
