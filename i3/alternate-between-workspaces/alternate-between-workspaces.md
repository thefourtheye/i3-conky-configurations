Th latest version of i3, comes with a feature to switch between workspaces,
like Windows' Alt + TAB functionality. You can keep the same key binding in
i3 as well. Open the `~/.i3/config` file and insert this line.

```
# switch between the current and the previously focused workspace
bindsym Mod1+Tab workspace back_and_forth
```

Now, restart i3 and enjoy :-)
