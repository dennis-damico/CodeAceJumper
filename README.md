# Code Ace Jumper

This extensions provides you with easy Ace Jump feature for Visual Studio Code. Ace Jump is fast cursor movement without touching neither the mouse nor cursor keys.

## Commands

- `extension.aceJump` when a key is specified, Code Ace Jumper matches each word's initial letter in the document. Words are identified by their separators (whitespaces, dots, squares, etc) which can be easily configured. Each initial letter is then marked with a unique char: by hitting a key, the cursor will be instantly moved in the corresponding position.

![example gif](https://media.giphy.com/media/l0HlFPNndZgxEHV6w/source.gif)

- `extension.aceJump.multiChar` allows us to refine the placeholders by providing more characters. When one matches it automatically jumps, otherwise you can escape and then jump by matching remaining placeholders.

![example gif](https://user-images.githubusercontent.com/2300328/53043799-17ad7e80-3468-11e9-993e-9d425a9801e8.gif)

## Keyboard shortcuts
You may set keyboard shortcuts for invoking Code Ace Jumper by entering values in the keybindings.json file. For example:

```json
{
    "key": "ctrl+alt+cmd+space",
    "command": "extension.aceJump"
},
{
    "key": "ctrl+cmd+space",
    "command": "extension.aceJump.selection"
}
```

Alternatively, you can set shortcuts using Code's own keyboard shortcuts GUI.

## Advanced visual configuration for the placeholder
Code Ace Jumper is preset with sensible visual defaults. You can further configure the aesthetics of the placeholders shown by adjusting the following settings in your settings.json file:

```json
aceJump.placeholder.width: placeholder width; defaults to 12
aceJump.placeholder.height: placeholder height; defaults to 14
aceJump.placeholder.fontSize: placeholder font size; defaults to 14
aceJump.placeholder.textPosX: placeholder text X position; defaults to 2
aceJump.placeholder.textPosY: placeholder text Y position; defaults to 12
aceJump.placeholder.fontWeight: placeholder font weight; defaults to normal
aceJump.placeholder.fontFamily: placeholder font family; defaults to Consolas
aceJump.placeholder.upperCase: placeholder font to uppercase; defaults to false
```

__Note__ that the placeholder is an SVG asset so amending the font and size, for example, will require you to also amend the X/Y text positions.

## Version history

### 1.0.0

Initial release

### 1.1.0

New group system when we have more matches than the alphabet can have (26) [details](https://github.com/lucax88x/CodeAceJumper/issues/6)

### 1.1.1

using SVG instead of TEXT for the decorations, this means a HUGE performance boost

### 1.1.2

thanks to [ncthis](https://github.com/lucax88x/CodeAceJumper/pull/8) we now are able to make ace jump placeholders only for a "range" where the cursor is, instead of full page. Genius workaround until vscode releases the APIs for getting only viewable area of the screen.

### 1.1.3

placeholder now have more configurations, such has font size, family, etc
added ', " and < in the pattern

### 1.1.4

- Added new command that let Ace Jump [details](https://github.com/lucax88x/CodeAceJumper/issues/6)
- Correctly disposing the `AceJump: Type` and `AceJump: Jump To messages`

### 1.1.5

- possibility to search inside words using the new setting `aceJump.finder.onlyInitialLetter=false`
- possibility to skip the search on the selections using the new setting `aceJump.finder.skipSelection=true`

### 1.1.6

- Resolve non-intuitive behavior when search query matches separator regex [details](https://github.com/lucax88x/CodeAceJumper/pull/20)

### 1.1.7

- Fixed "AceJump: Jump To" message always in status bar #18 [details](https://github.com/lucax88x/CodeAceJumper/issues/18)

### 1.1.8

- Now the icon does not move the charaters in vscode anymore #23 [details](https://github.com/lucax88x/CodeAceJumper/issues/23)

### 1.1.9

- Now uses a new vscode api for detecing the visible ranges in the screen [details](https://github.com/lucax88x/CodeAceJumper/issues/5)

### 1.1.10

- Now should work together with extensions using the TYPE command (like VIM extensions) thanks to [matklad](https://github.com/lucax88x/CodeAceJumper/pull/25)

### 2.0.0

- Total refactor of the code
- added a new command that support multichar [info](https://github.com/lucax88x/CodeAceJumper/issues/21)

### 2.0.1

- if while restricting we don't match a letter but we match a placeholder we jump directly for it

### 2.1.0

- dimming the editor when we start to ace jump, can be disabled with `aceJump.dim.enabled`

### 2.1.1

- reduced bundle size with webpack

### 2.1.2

- fixes [bug](https://github.com/lucax88x/CodeAceJumper/issues/29)

### 2.1.3

- fixes [bug](https://github.com/lucax88x/CodeAceJumper/issues/30)

### 2.1.4

- changed way to render highlights in the multichar and removed the limitation of 10

### 2.1.5

- now it uses full power of vscode api for multiple visible areas, for example when we collapse functions or classes

### 2.1.6

- updated readme, thanks to [pr](https://github.com/lucax88x/CodeAceJumper/pull/35)
- audited node packages for security
- when set to "only initial letter", first word of each line now works even with tabs indentation, [issue](https://github.com/lucax88x/CodeAceJumper/issues/33)

### 2.1.7

- audited node packages for security
- when using "selection mode", correctly selects also last character, [issue](https://github.com/lucax88x/CodeAceJumper/issues/108)
