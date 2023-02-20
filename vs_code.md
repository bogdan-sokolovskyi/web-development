## Список необходимых плагинов Visual Studio Code:

``` bash
1.	All Autocomplete
2.	Auto Close Tag
3.	Auto Complete Tag
4.	Auto Rename Tag
5.	EditorConfig for VS Code -or- Beautify
6.	Code Runner
7.	GitLens — Git supercharged
8.	Import Cost
9.	JavaScript (ES6) code snippets
10.	jshint
11.	Live Server
12.	Multiple clipboards for VSCode
13.	Path Autocomplete
14.	Reactjs code snippets
15.	Sass
16.	Theme - Oceanic Next
17.	vscode-icons
18.	ESLint
19. Prettier
20. indent-rainbow
```

## Fix code linter at on save click ctrl+s
Settings -> find 'codeActionsOnSave' -> Edit in settings.json -> add script ->
``` bash
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
},
```

## Add  default Terminal Git Bash
Settings -> find 'codeActionsOnSave' -> Edit in settings.json -> add script ->
``` bash
"terminal.integrated.profiles.windows": {
    "PowerShell": {
      "source": "PowerShell",
      "icon": "terminal-powershell"
    },
    "Command Prompt": {
      "path": [
        "${env:windir}\\Sysnative\\cmd.exe",
        "${env:windir}\\System32\\cmd.exe"
      ],
      "args": [],
      "icon": "terminal-cmd"
    },
    "GitBash": {
      "source": "Git Bash",
      "path": ["C:\\Program Files\\Git\\bin\\bash.exe"],
      "icon": "terminal-bash"
    }
},
"terminal.integrated.defaultProfile.windows": "GitBash",
```

# My work file settings.json
``` bash
{
    "workbench.colorTheme": "Oceanic Next",
    "workbench.iconTheme": "vscode-icons",
    "terminal.integrated.tabs.enabled": true,
    "editor.quickSuggestions": null,
    "html.format.contentUnformatted": "",
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "terminal.integrated.automationShell.osx": "",
    "terminal.integrated.profiles.windows": {
        "PowerShell": {
          "source": "PowerShell",
          "icon": "terminal-powershell"
        },
        "Command Prompt": {
          "path": [
            "${env:windir}\\Sysnative\\cmd.exe",
            "${env:windir}\\System32\\cmd.exe"
          ],
          "args": [],
          "icon": "terminal-cmd"
        },
        "GitBash": {
          "source": "Git Bash",
          "path": ["C:\\Program Files\\Git\\bin\\bash.exe"],
          "icon": "terminal-bash"
        }
    },
    "terminal.integrated.defaultProfile.windows": "GitBash",
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
    },
}
```
