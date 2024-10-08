# Zed IDE

[Zed](https://zed.dev/)
Code editor designed for high-performance collaboration with humans and AI.
Collection of my personal settings.

## Setup

Install the zed command line tool: `Zed > Install CLI`
To open a directory or file in Zed:
```zsh
zed /path/to/directory
```
To use Zed as your `$EDITOR` to edit Git commits etc, add to your shell profile:
```zsh
export EDITOR="zed --wait"
```

## Themes
Store new themes locally by placing them in the `~/.config/zed/themes` directory.

Override specific attributes of a theme:
```json
{
  "experimental.theme_overrides": {
    "editor.background": "#333",
    "syntax": {
      "comment": {
        "font_style": "italic"
      }
    }
  }
}
```

## Formatting
Configured at `~/.config/zed/settings.json`

Prettier for JavaScript:
```json
{
  "languages": {
    "JavaScript": {
      "formatter": {
        "external": {
          "command": "prettier",
          "arguments": ["--stdin-filepath", "{buffer_path}"]
        }
      }
    }
  }
}
```

## Key Bindings
Configured at `~/.config/zed/keymap.json`
Or, `Zed > Settings > Open Key Bindings`

Adding a custom key binding:
```json
[
  {
    "context": "Editor",
    "bindings": {
      "ctrl-w": "editor::SelectLargerSyntaxNode",
      "ctrl-shift-W": "editor::SelectSmallerSyntaxNode",
      "ctrl-c": "editor::Cancel"
    }
  }
]
```

Disabling a key binding:
```json
[
  {
    "context": "Editor",
    "bindings": {
      "alt-\\": null
    }
  }
]
```
