

# k-vim-vscode

vscode settings with vim key-bindings just like k-vim(https://github.com/wklken/k-vim)! Happy Coding! 

## 插件
- [Output Colorizer](https://marketplace.visualstudio.com/items?itemName=IBM.output-colorizer)
- [C/C++ Runner](https://marketplace.visualstudio.com/items?itemName=franneck94.c-cpp-runner)
- [CodeLLDB](https://marketplace.visualstudio.com/items?itemName=vadimcn.vscode-lldb)
- [C/C++ Extension Pack（C/C++, CMake Tools, Cmake, C/C++ Themes）](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools-extension-pack)
- GitHub Theme
- [Chinese (Simplified) (简体中文)](https://marketplace.visualstudio.com/items?itemName=MS-CEINTL.vscode-language-pack-zh-hans)
- Pylance
- Python
- Remote-SSH
- Vim
- [GDB Debug](https://marketplace.visualstudio.com/items?itemName=DamianKoper.gdb-debug)


## 说明
- 【Ctrl】+【` 】 ：打开默认终端，界面保留关闭前的状态；
- 【Ctrl】+【←】：上一个编辑器
- 【Ctrl】+【→】：下一个编辑器
- 【Ctrl】+【o】：跳转到上一个位置
- 【Ctrl】+【i】：跳转到下一个位置
- 【Ctrl】+【w】：关闭编辑器
- 【,】+【f】：按名称搜文件

## vscode settings.json

```javascript
{
    "files.autoSave": "onFocusChange",
    "remote.SSH.remotePlatform": {
        "yangyun": "linux"
    },
    "workbench.iconTheme": "Monokai Classic Icons",
    "workbench.colorTheme": "GitHub Dark",

    "files.exclude": {
        ".idea": true,
        ".vscode": true,
        "**/__pycache__": true,
        "**/*.pyc": true,
        "node_modules/": true,
        "templates_module/": true,
        "**/.project": true,
        ".mypy_cache/": true,
    },
    // ## Extension: vim
    "vim.leader": ",",
    "vim.incsearch": true,
    "vim.useCtrlKeys": true,
    "vim.hlsearch": true,
    "vim.highlightedyank.enable": true,

    // - references: https://code.visualstudio.com/docs/getstarted/keybindings#_default-keybindings
    // shortcut: kj
    // 退出编辑模式
    "vim.insertModeKeyBindings": [
        // - k-j to ESC
        {
            "before": ["k", "j"],
            "after": ["<Esc>"]
        }
    ],
    "vim.normalModeKeyBindingsNonRecursive": [
        // shortcut: leader-q
        // quit 关闭文件
        {
            "before": ["leader", "q"],
            "commands": [
                {
                    "command": "workbench.action.files.save",
                    "args": []
                },
                {
                    "command": "workbench.action.closeActiveEditor",
                    "args": []
                }
            ]
        },
        // shortcut: leader-w
        // save 保存文件
        {
            "before": ["leader", "w"],
            "commands": [
                {
                    "command": "workbench.action.files.save",
                    "args": []
                }
            ]
        },
        // shortcut: leader-gd
        // goToDefinition 跳转到定义处
        {
            "before": ["leader", "g", "d"],
            "after": ["g", "d"]
        },
        // shortcut: leader-jd
        // goToDefinition 跳转到定义处
        {
            "before": ["leader", "j", "d"],
            "after": ["g", "d"]
        },

        {
            "before": ["L"],
            "after": ["End"]
        },

        {
            "before": ["H"],
            "after": ["Home"]
        },

        {
            "before": ["space"],
            "after": ["/"]
        },

        // shortcut: leader-gh
        // show help-tip-def 展示提示
        {
            "before": ["leader", "g", "h"],
            "after": ["g", "h"]
        },
        // shortcut: leader-h
        // show help-tip-def 展示提示
        {
            "before": ["leader", "h"],
            "after": ["g", "h"]
        },
        // shortcut: leader-cc
        // comment 注释
        {
            "before": ["leader", "c", "c"],
            "commands": ["editor.action.addCommentLine"]
        },
        // shortcut: leader-cu
        // uncomment 解开注释
        {
            "before": ["leader", "c", "u"],
            "commands": ["editor.action.removeCommentLine"]
        },
        // shortcut: # and *
        // - switch # and *
        {
            "before": ["*"],
            "after": ["#"]
        },
        {
            "before": ["#"],
            "after": ["*"]
        },

        // shortcut: leader-f
        // go to file 跳转到文件
        {
            "before": ["leader", "f"],
            "commands": [
                "workbench.action.quickOpen",
            ]
        },
    ],
    "vim.visualModeKeyBindingsNonRecursive": [
        // shortcut: leader-cc
        // add comment 加注释
        {
            "before": ["<leader>", "c", "c"],
            "commands": ["editor.action.addCommentLine"]
        },
        // shortcut: leader-cu
        // uncomment 解开注释
        {
            "before": ["<leader>", "c", "u"],
            "commands": ["editor.action.removeCommentLine"]
        },
        // shortcut: > / <
        // indent/outdent lines (repeatable) 左右移动代码块
        {
            "before": [
                ">"             // shift + >
            ],
            "commands": [
                "editor.action.indentLines"
            ]
        },
        {
            "before": [
                "<"            // shift + <
            ],
            "commands": [
                "editor.action.outdentLines"
            ]
        },
    ],
    "editor.minimap.enabled": false,
    "editor.renderWhitespace": "none",
    "editor.renderControlCharacters": false,
    "workbench.activityBar.visible": true,
    "cmake.configureOnOpen": true,
    "vim.handleKeys": {
        "<C-f>": false,
        "<C-d>": false,
        "<C-k>": false,
    },
    // "window.zoomLevel": 0,
    // "editor.fontSize": 17,
    // "terminal.integrated.fontSize": 17,
}
```

## vscode keybindings.json

```javascript
[
    {
        "key": "ctrl+w",
        "command": "workbench.action.closeActiveEditor"
    },
    {
        "key": "ctrl+f4",
        "command": "-workbench.action.closeActiveEditor"
    },
    {
        "key": "ctrl+left",
        "command": "workbench.action.previousEditor"
    },
    {
        "key": "ctrl+pageup",
        "command": "-workbench.action.previousEditor"
    },
    {
        "key": "ctrl+right",
        "command": "workbench.action.nextEditor"
    },
    {
        "key": "ctrl+pagedown",
        "command": "-workbench.action.nextEditor"
    },
    {
        "key": "ctrl+j",
        "command": "-editor.action.joinLines",
        "when": "editorTextFocus"
    },
    // shortcut: ctrl+j/k
    // for quick open choose
    // ctrl+j/k 选择quickopen文件列表
    {
        "key": "ctrl+j",
        "command": "workbench.action.quickOpenSelectNext",
        "when": "inQuickOpen"
    },
    {
        "key": "ctrl+k",
        "command": "workbench.action.quickOpenSelectPrevious",
        "when": "inQuickOpen"
    },
    {
        "key": "ctrl+h",
        "command": "workbench.files.action.focusFilesExplorer"
    },
    {
        "key": "ctrl+k e",
        "command": "-workbench.files.action.focusOpenEditorsView",
        "when": "workbench.explorer.openEditorsView.active"
    },
    {
        "key": "ctrl+l",
        "command": "workbench.action.focusActiveEditorGroup",
        "when": "!terminalFocus"
    },
]
```


------

YunYang1994 于广州
