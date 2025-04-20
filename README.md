# LaTeX 报告模板

这是一个基于 [LaTeX-Beamer-Nankai](https://github.com/zshicode/LaTeX-Beamer-Nankai) 项目修改的 LaTeX 报告模板，专注于提供简洁的报告写作环境。

## 特性

- 支持 gb7714-2015 标准的参考文献格式
- 包含常用的 LaTeX 格式示例（列表、图片、表格、代码等）
- 使用 minted 包实现代码高亮
- 预配置的 VSCode 工作区设置
- 使用 XeLaTeX 编译引擎

## 使用方法

### 环境要求

1. 安装 TeX Live
2. 安装 VSCode
3. 安装 VSCode 的 LaTeX Workshop 插件
4. 安装 Python
5. 安装 Pygments（用于代码高亮）
   ```bash
   # 推荐使用 pipx 安装，可以避免污染全局 Python 环境
   pip install pipx
   pipx install Pygments==2.18.0
   
   # 或者直接使用 pip 安装
   pip install Pygments==2.18.0
   ```

### 项目结构

```
.
├── .vscode/
│ └── settings.json # VSCode工作区配置
├── report.tex # 报告主文件
├── reference.bib # 参考文献文件
└── tmp/ # 编译输出目录
```

### 编译方法

使用 VSCode 打开项目文件夹，打开 `report.tex` 文件，按下 `Ctrl+S` 保存时会自动触发编译，或者使用命令行：

```bash
xelatex -shell-escape report
biber report
xelatex -shell-escape report
xelatex -shell-escape report
```

注意：使用 minted 包时必须添加 `-shell-escape` 参数。

## minted 配置与报错说明

由于 TeX Live 更新导致 minted 包的使用方式存在差异，请根据您的环境选择正确的配置：

- **TeX Live 2024 及更早版本**（使用 Pygments 2.18.0）
  ```latex
  \usepackage[outputdir=./tmp]{minted}
  ```

- **TeX Live 2025 及更新版本**（使用 Pygments 2.18.0）
  ```latex
  \usepackage{minted}
  ```

您可以通过运行 `tlmgr --version` 命令查看当前安装的 TeX Live 版本，然后在 `report.tex` 文件中相应地调整 minted 包的导入语句。

如果编译过程中出现有关 minted 无法找到输出文件的错误，很可能是由于版本配置不匹配导致的。请根据上述指南进行调整。

## VSCode 配置说明

项目中的 `.vscode/settings.json` 已经预配置了 LaTeX 相关的设置，包括：

- 使用 XeLaTeX 作为编译器
- 配置了参考文献编译工具 biber
- 设置编译输出目录为 `./tmp`
- 配置了 PDF 预览等功能
- 添加了 `-shell-escape` 参数以支持 minted 包

这些配置会在打开项目时自动生效，无需额外设置。

## 参考

- 本项目修改自：[LaTeX-Beamer-Nankai](https://github.com/zshicode/LaTeX-Beamer-Nankai)
