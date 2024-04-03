
# Ethereum Security Bundle for vscode

A meta-extension bundling [vscode](https://marketplace.visualstudio.com/search?term=ethereum&target=VSCode&category=All%20categories&sortBy=Relevance) plugins for Smart Contract Auditors & Developres. This is basically [my](https://github.com/tintinweb) vscode auditing setup.

* [Bundled Extensions](#📚-bundled-extensions)
* [Tweaks](#⚙-tweaks)
* [More...](#➕-more-useful-extensions)
  


## 📚 Bundled Extensions

#### Solidity 

##### Language support

* [juanblanco.solidity](https://marketplace.visualstudio.com/items?itemName=juanblanco.solidity) - Solidity language support and more!
* [tintinweb.solidity-visual-auditor](https://marketplace.visualstudio.com/items?itemName=tintinweb.solidity-visual-auditor) - Security centric syntax and semantic highlighting, a detailed class outline and advanced Solidity code insights for Solidity developers and auditors.
* [tintinweb.solidity-metrics](https://marketplace.visualstudio.com/items?itemName=tintinweb.solidity-metrics) - Create fancy solidity code metrics reports.

##### Tool integrations

* [tintinweb.vscode-solidity-flattener](https://marketplace.visualstudio.com/items?itemName=tintinweb.vscode-solidity-flattener) - Flatten Solidity contracts from truffle projects from within vscode (context menu for solidity files in the vscode file explorer).

#### Vyper

##### Language support

* [tintinweb.vscode-vyper](https://marketplace.visualstudio.com/items?itemName=tintinweb.tintinweb.vscode-vyper) - Ethereum Vyper Language Support and Visual Auditor

#### LLL

##### Language support

* [tintinweb.vscode-LLL](https://marketplace.visualstudio.com/items?itemName=tintinweb.vscode-LLL) - Ethereum LLL Language Support

### General Purpose

##### Efficiency

* [streetsidesoftware.code-spell-checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - Spellcheck your code.
* [gimenete.github-linker](https://marketplace.visualstudio.com/items?itemName=gimenete.github-linker) - Right-Click and copy a github link of the selected code fragment to clipboard.

##### Review

* [ryu1kn.partial-diff](https://marketplace.visualstudio.com/items?itemName=ryu1kn.partial-diff) - Create partial diffs of selected text in the vscode text editor.
* [tintinweb.vscode-inline-bookmarks](https://marketplace.visualstudio.com/items?itemName=tintinweb.vscode-inline-bookmarks) - Easily add customizable inline bookmarks based on trigger words. Perfect for code audits or to keep track of notes and todo's.

##### Tool integrations

* [eamodio.gitlens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) - Git support. Especially useful when reviewing diffs.

## ⚙ Tweaks

Cool, you've come this far therefore I expect you're genuinely interested in either the individual extensions or you just installed the one-click bundle :) Either way, you're welcome!

Here's a quick walk-through and some tweaks on how to get the best out of vscode and the extensions.

*Note: json settings shown below are meant to be merged into your config.* 

### VSCode

**How do I un/install extensionbs?**

`AppMenu -> Preferences -> Extensions`

**How do I access vscode and extension settings?**

`AppMenu -> Preferences -> Settings`
  
**How do I disable telemetry in vscode?**

* Open settings.json (via vscode settings)
* Add this to `settings.json`:
```json
{
    "telemetry.enableCrashReporter": false,
    "telemetry.enableTelemetry": false,
}
```

**Make vscode auto-save files automatically after a delay**

* It can be annoying that you are editing a file and always have to manually save it for it to be synced to the file-system. The following auto-saves files after a delay automatically.
* Add this to `settings.json`:
```json
{
  "files.autoSave": "afterDelay",
}
```

* And disable confirmation when deleting

```json
{
  "explorer.confirmDelete": false,
}
```

**How do I extend the terminal scrollback cache?** 

* Some tools may produce a large amount of output lines and it can be annoying that the integrated terminal's scrollback is very limited.

* Add this to `settings.json`:
```json
{
  "terminal.integrated.scrollback": 6000,
}
```

**Selection Highlighting**

![image](https://user-images.githubusercontent.com/2865694/60887684-3cf32b80-a255-11e9-976f-810ea27da218.png)

* Grey selection highlight
* Orange selection border for other occurences of the selection in the editor (nice for comparison)

```json
{
  "workbench.colorCustomizations": {
        "editor.selectionBackground": "#977f5746",
        "editor.selectionHighlightBackground": "#cf9b4d28",
        "editor.selectionHighlightBorder":"#ff5e0096"
    },
}
```

**Make vscode diff editor ignore whitespaces by default**

* we don't care too much about whitespaces right now :D 

```json
{
  diffEditor.ignoreTrimWhitespace
}
```

### Solidity

**Disable the auto-linting**

* Add this to `settings.json`:
```json
{
  "solidity.enabledSolium": false,
  "solidity.linter": "",
}
```

### Git & Gitlens

* Gitlens code-lenses can be annoying (inline code actions). Thankfully they can be disabled (together with telemetry. data privacy ftw). We also enable git commit fetching for the git extension:

```json
{
  "gitlens.codeLens.enabled": false,
  "gitlens.advanced.telemetry.enabled": false,
  "git.autofetch": true,
}
```
 
## ➕ More useful extensions

* Indent-Rainbow
* Bookmarks
* Git Graph
* ES Lint
* XML Tools
* Material Icon Theme
* Markdown All in One

## Notes

* You can uninstall individual extensions at any point.
* Uninstalling the extension pack will uninstall all the referenced extensions.

## Credits

♥ Thanks to the awesome Ethereum community for building all these extensions, you rock!


## Release Notes

see [CHANGELOG](./CHANGELOG.md)


-----------------------------------------------------------------------------------------------------------
