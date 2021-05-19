# atcoder-pyenv
Environment for doing AtCoder in Python

## Requiements
- Docker
- VScode
- VSCode Remote Container (vscode extention)

## Setup
Git clone this repository
```bash
$ git clone https://github.com/miya/atcoder-pyenv
```

Open the container in Vscode
```
Open folder in Conteiner
```

Login with online judge tools
```bash
$ oj login https://atcoder.jp/
```

Login with atcoder-cli
```bash
$ acc login
```

## Keybind
Add the following to keybindings.json
```json
[
  {
    "key": "ctrl+e",
    "command": "workbench.action.tasks.runTask",
    "when": "editorTextFocus",
    "args": "execution",
  },
  {
    "key": "ctrl+n",
    "command": "workbench.action.tasks.runTask",
    "args": "new",
  },
  {
    "key": "ctrl+t",
    "command": "workbench.action.tasks.runTask",
    "when": "editorTextFocus",
    "args": "test",
  },
  {
    "key": "ctrl+s",
    "command": "workbench.action.tasks.runTask",
    "when": "editorTextFocus",
    "args": "submit",
  }
]
```