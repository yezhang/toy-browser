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