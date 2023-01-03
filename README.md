# 部署环境

Arch Linux (WSL2)

# 流程详解

采用 GitHub Pages 来部署 blog。首先创建名为`username.GitHub.io`的`Repository`。

安装必要组件：`sudo pacman -S hugo git`

部署`Hugo`组件：`hugo new site .`

必要时，添加`--force`

添加主题文件，此处采用[dsrkafuu/hugo-theme-fuji: A minimal Hugo theme with nice theme color. | 一个主题色极简 Hugo 主题。](https://github.com/dsrkafuu/hugo-theme-fuji/)

```sh
git submodule add https://github.com/dsrkafuu/hugo-theme-fuji.git themes/fuji
```

（维护）更新主题使用：`git submodule update --remote --merge`

运行`hugo server --theme=fuji --buildDrafts`，即可展示页面效果。

运行`hugo --theme=fuji`，即可部署至`public`目录。

切换至`public`目录，运行：

```sh
git init
git branch -M main
git remote add origin https://github.com/CIawa-ob/CIawa-ob.github.io.git
```
由于宿主机内已经安装 vscode 编辑器，运行:

```sh
code .
```

即可在弹出的 vscode 页面中完成提交操作。

访问 GitHub Pages 即可看到部署结果。

---

其余页面配置参见`config.toml`

# 参考文档

[GitHub Pages 搭建教程 - 少数派](https://sspai.com/post/54608)

[Quick Start |Hugo](https://gohugo.io/getting-started/quick-start/)

[Hugo中文文档](https://www.gohugo.org/)