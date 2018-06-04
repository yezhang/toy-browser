## 调试 Rust
首先配置好 Cargo，保证执行 cargo 命令时，程序可以正常运行：
cargo build  
cargo run  

配置 vs code 调试启动文件：(__.vscode/launch.json__)

调试主程序：
```javascript
{
    "type": "lldb",
    "request": "launch",
    "name": "Launch Main",
    "cwd": "${workspaceRoot}",
    // "cargo": { //debug test
    //     "args": [
    //         "test", "--no-run", "--lib" 
    //     ],
    //     "filter": { "kind": "lib" }
    // },
    "cargo": { //debug main
        "args": [
            "build"
        ],
        "filter": { "kind": "bin" }
    },
    "args":[],
    "sourceLanguages": ["rust"]
}
```

调试测试程序：
```javascript
{
    "type": "lldb",
    "request": "launch",
    "name": "Launch Main",
    "cwd": "${workspaceRoot}",
    "cargo": { //debug test
        "args": [
            "test", "--no-run", "--lib" 
        ],
        "filter": { "kind": "lib" }
    },
    // "cargo": { //debug main
    //     "args": [
    //         "build"
    //     ],
    //     "filter": { "kind": "bin" }
    // },
    "args":[],
    "sourceLanguages": ["rust"]
}
```

## 参考资料
1. vscode-lldb 对于 Rust 和 Cargo 的支持：https://github.com/vadimcn/vscode-lldb/blob/master/MANUAL.md#rust-language-support

