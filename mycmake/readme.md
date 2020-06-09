# 说明


## 配置

* 配置launch

> 可自动创建

```
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "(gdb) 启动",
            "type": "cppdbg",
            "request": "launch",
            "program": "${workspaceFolder}/build/cmakedemo",
            "args": [],
            "stopAtEntry": false,
            "cwd": "${workspaceFolder}",
            "environment": [],
            "externalConsole": false,
            "MIMode": "gdb",
            "setupCommands": [
                {
                    "description": "为 gdb 启用整齐打印",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                }
            ],
            "preLaunchTask":  "build"
        }
    ]
}
```


* 配置tasks

> 新建文件：Terminal => Configure Tasks

```
{
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "2.0.0",
    "tasks": [
        {
            "label": "build",
            "type": "shell",
            "command": "cd build; cmake ..; make",
            "group": {
                "kind": "build",
                "isDefault": true
            }
        },
        {
            "label": "clean",
            "type":  "shell",
            "command": "make clean"
        }
    ]
}
```

* CMake

```
cmake_minimum_required( VERSION 2.8 )
project( cmakedemo )

aux_source_directory(. DIR_SRCS)

add_executable( cmakedemo  ${DIR_SRCS} )

add_definitions("-Wall -g")   # 调试
```



## build（手动build）

```
mkdir build
cd build
cmake ..
make
./cmakedemo
```


## build & 执行 & 调试

* 调试: `F5` 
  
* 执行: `Ctrl+F5`


