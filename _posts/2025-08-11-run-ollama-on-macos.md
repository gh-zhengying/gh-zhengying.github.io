---
title: "MacOS 使用 Ollama 部署本地模型"
categories:
  - AI
tags:
  - MacOS
  - Ollama
---

## 1. 安装 Homebrew

> 非科学上网执行第二个从 `gitee.com` 安装

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

```shell
/bin/bash -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
```

## 2. 安装/启动 Ollama

```shell
brew install ollama
```

```shell
brew services start ollama
```

## 3. 下载模型

> [查找模型名称](https://ollama.com/search) 

```shell
ollama run deepseek-r1:1.5b
```

## 4. 开放访问

编辑 `/opt/homebrew/opt/ollama/homebrew.mxcl.ollama.plist` 添加如下环境变量开放访问

```xml
<key>EnvironmentVariables</key>
<dict>
    <key>OLLAMA_HOST</key>
    <string>0.0.0.0</string>
</dict>
```
