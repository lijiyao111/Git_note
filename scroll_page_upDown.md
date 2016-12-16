# added key shortcut to sublime text 3, to scroll page up and down

1. Save the following python script as *ScrollLinesFixedCommand.py* and put into the *Package User* directory
```python
# Credit: https://forum.sublimetext.com/t/st2-how-to-page-up-down-without-moving-the-cursor/10434/4
import sublime, sublime_plugin
class ScrollLinesFixedCommand(sublime_plugin.TextCommand):
	"""Must work exactly as builtin scroll_lines command, but without moving the cursor when it goes out of the visible area."""
	def run(self, edit, amount, by="lines"):
		# only needed if one empty selection
		if by != "lines" or (len(self.view.sel()) == 1 and self.view.sel()[0].empty()):
			maxy = self.view.layout_extent()[1] - self.view.line_height()
			curx, cury = self.view.viewport_position()
			if by == "pages":
				delta = self.view.viewport_extent()[1]
			else:
				delta = self.view.line_height()
			nexty = min(max(cury - delta * amount, 0), maxy)
			self.view.set_viewport_position((curx, nexty))
		else:
			self.view.run_command("scroll_lines", {"amount": amount})
```

2. Add the following key bindings into Preferences->Key bindings:
```
[
  { "keys": ["alt+up"], "command": "swap_line_up" },
  { "keys": ["alt+down"], "command": "swap_line_down" },
  { "keys": ["ctrl+alt+up"], "command": "scroll_lines_fixed", "args": {"by": "pages", "amount": 0.95 } },
  { "keys": ["ctrl+alt+down"], "command": "scroll_lines_fixed", "args": {"by": "pages", "amount": -0.95 } }
]
```