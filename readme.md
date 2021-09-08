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