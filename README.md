
# VSCode Ethereum Security Bundle

A meta-extension bundling [vscode marketplace](https://marketplace.visualstudio.com/search?term=ethereum&target=VSCode&category=All%20categories&sortBy=Relevance) plugins for secure Ethereum smart contract development.

* [What's the story?](#whats-the-story)
* [What's included?](#-whats-included)
  * [I want (extension-name-here) to be part of this awesome bundle! Where to go?](#whats-included)
  * [(extension-name-here) is sh*t! How to get it removed from the bundle?](#whats-included)
* [Alright, it's installed, any other settings and tweaks you want to share?](#tweaks)
* [Other useful extensions, not bunled with this one](#other-useful-extensions)
  
## What's the story?


* You (👦👧) are developing or auditing smart contracts for the Ethereum ecosystem 💻.
* (optional) You ❤ `git` and your 🏠 is [github](https://github.com/).
* You are battling ⚡ with all the different IDE's that claim to support smart contract languages but they do not seem to be the right fit 😐.
* The IDE's by default do not sufficiently support you in doing a good job out of the box and the IDE's marketplace 🍏🍌🍉(or contrib. extensions) offer an overwhelming amount of extensions 🀄.

💡 I've been there and am now stuck on [vscode](https://code.visualstudio.com/) as the defacto IDE for all things Ethereum smart contract. I require an IDE that allows me to navigate large code-bases efficiently, preferably without wasting time. Especially with the risk profile of smart contracts I am very interested in an IDE the passively and actively supports me in writing secure code and makes me aware of functionality that is exposed or state-modifying.

That's why I publish this meta-extension that does not contribute any functionality by its own, but installs a curated set of useful extensions commonly found on the [vscode marketplace](https://marketplace.visualstudio.com/search?term=ethereum&target=VSCode&category=All%20categories&sortBy=Relevance). 🤓

## 😎 What's included?

Feel like an extension is missing or should be removed from the bundle? Create an [issue](https://github.com/tintinweb/vscode-ethereum-security-bundle/issues) and vote for an extension to be accepted or removed! Together we can make this work for everyone :)  

#### Solidity 

##### Language support

* [juanblanco.solidity](https://marketplace.visualstudio.com/items?itemName=juanblanco.solidity) - Solidity language support and more!
* [beaugunderson.solidity-extended](https://marketplace.visualstudio.com/items?itemName=beaugunderson.solidity-extended) - Solidity support that aims to enable all of Visual Studio Code's features. 
* [hosho.solidity-debugger](https://marketplace.visualstudio.com/items?itemName=hosho.solidity-debugger) - A Debugger for Solidity smart contracts - powered by the Meadow testing and development tool suite.
* [tintinweb.solidity-visual-auditor](https://marketplace.visualstudio.com/items?itemName=tintinweb.solidity-visual-auditor) - Security centric syntax and semantic highlighting, a detailed class outline and advanced Solidity code insights for Solidity developers and auditors.

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

##### Tool integrations

* [eg2.vscode-npm-script](https://marketplace.visualstudio.com/items?itemName=eg2.vscode-npm-script) - NPM integration for vscode. Install dependencies directly by right-clicking `package.json` in your vscode file explorer.
* [eamodio.gitlens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) - Git support. Especially useful when reviewing diffs.

## Tweaks

Cool, you've come this far therefore I expect you're genuinely interested in either the individual extension or you just installed the one-click bundle :) Either way, you're welcome!

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
 
## Other useful extensions

* Indent-Rainbow
* Bookmarks
* Git Graph
* ES Lint
* XML Tools
* Material Icon Theme
* Markdown All in One


## Credits

♥ Thanks to the awesome Ethereum community for building all these extensions, you rock!


## Release Notes

see [CHANGELOG](./CHANGELOG.md)


-----------------------------------------------------------------------------------------------------------
