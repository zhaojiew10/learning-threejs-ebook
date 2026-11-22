# Threejs编程指南

**《Learning Three.js: The JavaScript 3D Library for WebGL, Second Edition》** 的中文电子书，使用 **MkDocs Material + Markdown** 构建。

## 内容说明

- **纯中文阅读**：网站仅包含中文内容，不提供英文全文栏目或英文 PDF 下载。
- **完整章节**：12 章正文，共 12 个中文 Markdown 文件；不以摘要代替正文。
- **术语规则**：关键术语首次出现时采用“中文（English）”，后文使用中文；API、类名、属性、文件名和代码保留英文。
- **本地资源**：中文正文、插图和动画随站点构建，阅读不依赖外部图片服务。

> 原书及插图的版权归原作者和出版方所有。公开部署或再分发本书内容和插图前，请确认拥有相应权利或授权。详见 [NOTICE.md](NOTICE.md)。

## 完整性与构建验证

- **384 个内部页码标记**用于逐页比对和漏译检查，不在正文中显示。
- **216 张正文插图**全部保留并通过解码检查。
- **全部实际代码块**保持缩进、注释和字符串不变；名称列表以表格呈现。
- 使用 `mkdocs build --strict` 和构建后 HTML 资源检查发现失效链接。

## 本地预览

### Windows PowerShell

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m mkdocs serve -a 0.0.0.0:8001
```

### Linux / macOS

```bash
python3 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
.venv/bin/python -m mkdocs serve -a 0.0.0.0:8001
```

本机打开 <http://127.0.0.1:8001>。监听 `0.0.0.0` 时，同一局域网设备也可通过本机局域网 IP 的 `8001` 端口访问；如连接失败，请检查防火墙。按 `Ctrl+C` 停止服务。

## 构建静态网站

```bash
python -m mkdocs build --strict
```

Windows 下也可以执行：

```powershell
.\.venv\Scripts\python.exe -m mkdocs build --strict
```

静态网站输出到 `site/`。`--strict` 会将文档警告视为构建错误。

## 项目结构

```text
.
├── docs/
│   ├── chapters-zh/        # 第二版中文内容（12 章）
│   ├── resources/         # 中文页面引用的插图
│   ├── terminology.md
│   └── stylesheets/
├── .github/workflows/     # GitHub Pages 自动构建与发布
├── mkdocs.yml
├── requirements.txt
├── NOTICE.md
└── README.md
```

仓库只包含电子书内容、站点配置和 Pages 工作流；制作脚本、中间产物、原始资料及第四版源码不会发布到此仓库。

## 发布到 GitHub Pages

`.github/workflows/deploy.yml` 会在推送到 `main` 后自动执行严格构建并发布 `site/`。仓库的 **Settings → Pages → Build and deployment → Source** 需要选择 **GitHub Actions**。

站点地址为 <https://zhaojiew10.github.io/learning-threejs-ebook/>。

## 来源

- [原始 PDF 获取页面（Packt 官方，按出版方条件领取）](https://packt.link/free-ebook/9781784392215)。
- 第四版代码：<https://github.com/PacktPublishing/Learn-Three.js-Fourth-edition>（MIT License，以其仓库中的 `LICENSE` 为准）。
- 站点组织方式参考：<https://github.com/zhaojiew10/cuda-ebook>。
