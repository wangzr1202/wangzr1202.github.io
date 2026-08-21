# Zirui Wang — Personal Homepage

这是一个为 GitHub Pages 准备的轻量学术个人主页。它保留了参考页面的纸张质感、手写标题、学术简介、news 时间线和 selected papers 布局，但移除了 Jekyll、Ruby、Docker、插件、BibTeX、博客、CV 数据系统等当前不需要的功能。

整个网站只有原生 HTML 与 CSS，不需要安装依赖，也不需要构建。

## 文件结构

```text
.
├── index.html                    # 页面内容；主要编辑这个文件
├── styles.css                    # 页面样式
├── assets/
│   ├── favicon.svg               # 浏览器标签图标
│   └── portrait-placeholder.svg  # 头像占位图
├── .nojekyll                     # 告诉 GitHub Pages 直接发布静态文件
├── LICENSE                       # MIT 开源许可证
└── NOTICE                        # 参考来源与致谢
```

## 如何替换成自己的内容

在 `index.html` 中搜索 `TODO:`，依次修改：

1. 姓名与页面标题；
2. 两段个人介绍；
3. 邮箱、GitHub、Google Scholar、LinkedIn 和 CV 链接；
4. 头像：用自己的图片替换 `assets/portrait-placeholder.svg`，并同步修改 `<img src="...">`；
5. news：复制或删除 `.news-entry`；
6. 论文：复制或删除 `.paper`，填写标题、作者、会议和链接。

论文链接目前故意使用 `<span>`，避免占位链接跳转到错误页面。补充真实链接时，例如将：

```html
<span>paper</span>
```

替换为：

```html
<a href="https://arxiv.org/abs/xxxx.xxxxx">paper</a>
```

如需论文预览图，可将 `.paper-preview` 替换为：

```html
<img class="paper-image" src="assets/your-paper-preview.png" alt="Preview of the paper">
```

并在 `styles.css` 中为 `.paper-image` 添加与 `.paper-preview` 相同的宽高。

## 本地预览

在仓库目录运行：

```bash
python3 -m http.server 8000
```

然后访问 <http://localhost:8000>。

## 发布到 GitHub Pages

提交并推送文件：

```bash
git add .
git commit -m "Build personal homepage"
git push origin main
```

在仓库的 **Settings → Pages** 中选择：

- Source: `Deploy from a branch`
- Branch: `main`
- Folder: `/(root)`

### 关于当前仓库名称

当前 Git remote 的仓库所有者是 `wangzr1202`，仓库名是 `wangzirui.github.io`。如果你希望根地址是 `https://wangzr1202.github.io/`，仓库必须重命名为 `wangzr1202.github.io`。保持当前名称时，它通常会作为项目页面发布在 `https://wangzr1202.github.io/wangzirui.github.io/`。

本项目全部使用相对路径，因此两种地址都可以正常加载资源。

## References & acknowledgements

页面的视觉方向与内容层次参考了：

- [Ying Wang's homepage](https://yingwangg.github.io/)
- [YingWANGG.github.io source repository](https://github.com/YingWANGG/YingWANGG.github.io)
- [al-folio](https://github.com/alshedivat/al-folio), the MIT-licensed academic website theme used by the reference project

本项目没有复制参考仓库完整的 Jekyll 工具链，也没有复用其个人照片、简介、论文数据或论文图片；主页被重新实现为更容易理解和维护的静态版本。更完整的 attribution 见 [NOTICE](NOTICE)。

## License

代码以 [MIT License](LICENSE) 开源。欢迎学习、修改和分享；如果你基于本项目继续创作，也建议保留相应的引用和许可证说明。
