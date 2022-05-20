# k-vim-vscode

vscode settings with vim key-bindings just like k-vim(https://github.com/wklken/k-vim)! Happy Coding! 

## 说明
- 【Ctrl】+【` 】 ：打开默认终端，界面保留关闭前的状态；
- 【Ctrl】+【←】：后退
- 【Ctrl】+【→】：前进
- 【Alt】+【←】：上一个编辑器
- 【Alt】+【→】：下一个编辑器
- 【Ctrl】+【w】：关闭编辑器
- 【,】+【f】：按名称搜文件

## vscode settings.json

```javascript
{
    "files.autoSave": "onFocusChange",
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
}
```

## vscode keybindings.json

```javascript
[
    {
        "key": "ctrl+right",
        "command": "workbench.action.navigateForward"
    },
    {
        "key": "alt+right",
        "command": "-workbench.action.navigateForward"
    },
    {
        "key": "ctrl+left",
        "command": "workbench.action.navigateBack"
    },
    {
        "key": "alt+left",
        "command": "-workbench.action.navigateBack"
    },
    {
        "key": "ctrl+w",
        "command": "workbench.action.closeActiveEditor"
    },
    {
        "key": "ctrl+f4",
        "command": "-workbench.action.closeActiveEditor"
    },
    {
        "key": "alt+left",
        "command": "workbench.action.previousEditor"
    },
    {
        "key": "ctrl+pageup",
        "command": "-workbench.action.previousEditor"
    },
    {
        "key": "alt+right",
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
    }
]
```


------

YunYang1994 于广州
