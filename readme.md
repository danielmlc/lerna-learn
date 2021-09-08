lerna

##### 全局安装

``` bash
npm i -g lerna
```

#### 常用命令

```bash

# 初始化lerna项目默认为固有模式
lerna init 
lerna init --independent #独立模式 

#所有包都添加某个依赖
lerna add packsges name 

# 查看依赖项列表
lerna list

# 下载依赖项目的依赖包
lerna bootstrap

# 创建新依赖项
lerna create packages

# 发布包
lerna publish


```

#### 命令列表
 | 命令        | 价格    |
 | --------   | :-----  |
| lerna bootstrap	| 安装依赖 |
| lerna clean	| 删除各个包下的node_modules |
| lerna init	| 创建新的lerna库 |
| lerna list	| 显示package列表 |
| lerna changed	| 显示自上次relase tag以来有修改的包， 选项通 list |
| lerna diff	| 显示自上次relase tag以来有修改的包的差异， 执行 git diff |
| lerna exec	| 在每个包目录下执行任意命令 |
| lerna run	| 执行每个包package.json中的脚本命令 |
| lerna add	| 添加一个包的版本为各个包的依赖 |
| lerna import	| 引入package |
| lerna link	| 链接互相引用的库 |
| lerna create	| 新建package |
| lerna publish	| 发布 |


> lerna.json 配置说明

```json
{
  "npmClient": "yarn", // 执行命令所用的客户端，默认为npm —— 配置后会强制使用最佳实践：能用yarn的用yarn——如lerna bootstap --hoist不再可用
  "command": { // 命令相关配置
    "publish": { // 发布时配置
       "allowBranch": "master", // 只在master分支执行publish
      "conventionalCommits": true, // 生成changelog文件
      "exact": true, // 准确的依赖项
      "ignoreChanges": ["ignored-file", "*.md"], // 发布时忽略的文件
      "message": "chore(release): publish" // 发布时的自定义提示消息
    },
    "bootstrap": { // 安装依赖配置
      "ignore": "component-*", // 忽略项
      "npmClientArgs": ["--no-package-lock"], // 执行 lerna bootstrap命令时传的参数
      "hoist": true
    },
    "version": {
      "conventionalCommits": true //开启日志：自动生成changLog.md
    }
  },
  "packages": [ // 指定存放包的位置
    "packages/*"
  ],
  "version": "0.0.0" // 当前版本号  如果为独立版本模式 配置值应为independent
}

```