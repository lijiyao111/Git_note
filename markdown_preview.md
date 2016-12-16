# install Markdown Preview for markdown files

## Easiest way for installation:
Using Package Control (Recommended)

For all Sublime Text 2/3 users we recommend install via Package Control.

1. Install Package Control if you haven't yet.
2. Use cmd+shift+P then Package Control: Install Package
3. Look for Markdown Preview and install it.

## to Preview:

* use cmd+shift+P then Markdown Preview to show the follow commands (you will be prompted to select which parser you prefer):
    * Markdown Preview: Preview in Browser
    * Markdown Preview: Export HTML in Sublime Text
    * Markdown Preview: Copy to Clipboard
    * Markdown Preview: Open Markdown Cheat sheet
* or bind some key in your user key binding, using a line like this one: { "keys": ["ctrl+q"], "command": "markdown_preview", "args": {"target": "browser", "parser":"github"} }, for a specific parser and target or { "keys": ["alt+m"], "command": "markdown_preview_select", "args": {"target": "browser"} }, to bring up the quick panel to select enabled parsers for a given target


### support for Matjax:
in Preferences->Pacakge Settings -> Markdown Preview -> Settings-User, Overwrite the *enable_mathjax* option to be **true** (find the setting in Settings-default), then the following equaiton should be able to display correctly:
$$
\frac{\partial^2 u}{\partial t^2}=c^2 \nabla^2 u 
$$


For more informaiton, check this link: (https://github.com/revolunet/sublimetext-markdown-preview)