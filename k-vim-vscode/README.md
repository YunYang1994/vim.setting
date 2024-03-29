

# k-vim-vscode

vscode settings with vim key-bindings just like [k-vim](https://github.com/YunYang1994/vim.setting/tree/master/k-vim)! Happy Coding! 

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
- [Path Autocomplete](https://marketplace.visualstudio.com/items?itemName=ionutvmi.path-autocomplete)
- [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)
- [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)
- [GDB Debug](https://marketplace.visualstudio.com/items?itemName=DamianKoper.gdb-debug)


## 说明
- 【Ctrl】+【` 】 ：打开默认终端，界面保留关闭前的状态；
- 【Ctrl】+【←】：上一个编辑器
- 【Ctrl】+【→】：下一个编辑器
- 【Ctrl】+【i】：跳转到上一个位置
- 【Ctrl】+【w】：关闭编辑器
- 【,】+【f】：按名称搜文件
- 对于 markdown 文件，右键点击【MPE: 打开侧边预览】即可一边编辑一边预览

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
        {
            "before": ["L"],
            "after": ["End"]
        },
        {
            "before": ["H"],
            "after": ["Home"]
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
    "C_Cpp.errorSquiggles": "Disabled",
    "cmake.configureArgs": [
        "-Wno-dev",
        "-Wno-deprecated"
    ],
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
    {
        "key": "ctrl+k ctrl+k",
        "command": "-deleteAllRight",
        "when": "editorTextFocus && !editorReadonly"
    },
    {
        "key": "ctrl+o",
        "command": "-workbench.action.files.openFileFolder",
        "when": "isMacNative && openFolderWorkspaceSupport"
    },
    {
        "key": "ctrl+o",
        "command": "-workbench.action.files.openFile",
        "when": "true"
    },
    {
        "key": "ctrl+o",
        "command": "-workbench.action.files.openFolderViaWorkspace",
        "when": "!openFolderWorkspaceSupport && workbenchState == 'workspace'"
    },
    {
        "key": "ctrl+o",
        "command": "-extension.vim_ctrl+o",
        "when": "editorTextFocus && vim.active && vim.use<C-o> && !inDebugRepl"
    },
    {
        "key": "ctrl+o",
        "command": "-workbench.action.files.openLocalFile",
        "when": "remoteFileDialogVisible"
    },
    {
        "key": "ctrl+o",
        "command": "workbench.action.navigateForward",
        "when": "canNavigateForward"
    },
    {
        "key": "alt+right",
        "command": "-workbench.action.navigateForward",
        "when": "canNavigateForward"
    },
    {
        "key": "ctrl+i",
        "command": "-extension.vim_ctrl+i",
        "when": "editorTextFocus && vim.active && vim.use<C-i> && !inDebugRepl"
    },
    {
        "key": "ctrl+i",
        "command": "-markdown.extension.editing.toggleItalic",
        "when": "editorTextFocus && !editorReadonly && editorLangId == 'markdown'"
    },
    {
        "key": "ctrl+i",
        "command": "-toggleSuggestionDetails",
        "when": "suggestWidgetVisible && textInputFocus"
    },
    {
        "key": "ctrl+i",
        "command": "-editor.action.triggerSuggest",
        "when": "editorHasCompletionItemProvider && textInputFocus && !editorReadonly"
    },
    {
        "key": "ctrl+i",
        "command": "workbench.action.navigateBack",
        "when": "canNavigateBack"
    },
    {
        "key": "alt+left",
        "command": "-workbench.action.navigateBack",
        "when": "canNavigateBack"
    },
]
```


------

YunYang1994 于广州
