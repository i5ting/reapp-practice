# reapp-practice
http://reapp.io/


## install 

Installation is done through npm:

```
sudo npm install -g reapp
```

既然是npm，那咱就扒一下[package.jsoon](https://github.com/reapp/reapp/blob/master/package.json)


```
"dependencies": {
    "colors": "~1.0.3",
    "commander": "^2.6.0",
    "es6-promise": "^2.0.1",
    "mkdirp": "^0.5.0",
    "ncp": "~1.0.1",
    "reapp-object-assign": "^1.0.0",
    "reapp-pack": "^1.3.19",
    "reapp-server": "^1.0.1",
    "replace": "~0.3.0",
    "rimraf": "~2.2.8"
  },
  "bin": {
    "reapp": "./bin/reapp",
    "reapp-new": "./bin/reapp-new",
    "reapp-build": "./bin/reapp-build",
    "reapp-run": "./bin/reapp-run",
    "reapp-debug": "./bin/reapp-debug"
  }
```

说明

- dependencies是依赖的npm
- bin指的是可以执行的命令，从依赖看，是commander做cli解析


它既然有cli，那么我就看一下它有哪些功能

```
 reapp --help

  Usage: reapp [options] [command]


  Commands:

    new [name] [template]  creates a directory with a new reapp-starter scaffold, name required but template optional
    run [platform]         runs a reapp application with express/webpack-dev-server
    build [platform]       builds a reapp application to a bundle in ./build
    debug                  outputs debug information, use this when opening issues!
    help [cmd]             display help for [cmd]

  Options:

    -h, --help     output usage information
    -V, --version  output the version number

```

目前只有5个大功能，还比较简单

- new 新建
- run 运行
- build 打包构建
- debug 调试
- help  帮助


## helloworld


Generate a new base reapp stack with:

```
➜  examples git:(master) ✗ reapp new helloworld

Creating new reapp folder for: helloworld...
Running git clone --depth=1 https://github.com/reapp/starter-default /Users/sang/workspace/github/reapp-practice/examples/helloworld...
Running git init...
Inserting your name...
Running npm install...
Running npm dedupe react...
Done!
```

这里它是从https://github.com/reapp/starter-default作为项目模板拷贝，和ionic的做法类似。




And finally in your app directory, run it on localhost:3010:

```
cd helloworld 
reapp run

Your app is running on http://localhost:3010

Building with Webpack...
Hash: 032b6ab76ce5b7404bbd
Version: webpack 1.8.5
Time: 3443ms


```

