# LaTeX 报告模板

这是一个基于 [LaTeX-Beamer-Nankai](https://github.com/zshicode/LaTeX-Beamer-Nankai) 项目修改的 LaTeX 报告模板，专注于提供简洁的报告写作环境。

## 特性

- 支持 gb7714-2015 标准的参考文献格式
- 包含常用的 LaTeX 格式示例（列表、图片、表格、代码等）
- 预配置的 VSCode/Cursor 工作区设置
- 使用 XeLaTeX 编译引擎

## 使用方法

### 环境要求

1. 安装 TeX Live
2. 安装 VSCode 或 Cursor
3. 安装 VSCode 或 Cursor 的 LaTeX Workshop 插件

### 项目结构

```
.
├── .vscode/
│ └── settings.json # VSCode/Cursor 工作区配置
├── report.tex # 报告主文件
├── reference.bib # 参考文献文件
└── tmp/ # 编译输出目录
```

### 编译方法

使用 VSCode/Cursor 打开项目文件夹，打开 `report.tex` 文件，按下 `Ctrl+S` 保存时会自动触发编译，或者使用命令行：

```bash
xelatex report
biber report
xelatex report
xelatex report
```

## VSCode/Cursor 配置说明

项目中的 `.vscode/settings.json` 已经预配置了 LaTeX 相关的设置，包括：

- 使用 XeLaTeX 作为编译器
- 配置了参考文献编译工具 biber
- 设置编译输出目录为 `./tmp`
- 配置了 PDF 预览等功能

这些配置会在打开项目时自动生效，无需额外设置。

## 参考

- 本项目修改自：[LaTeX-Beamer-Nankai](https://github.com/zshicode/LaTeX-Beamer-Nankai)