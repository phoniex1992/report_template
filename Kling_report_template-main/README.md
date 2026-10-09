# Kling_report_template

# Kling Report LaTeX Template 使用说明

本压缩包包含了一套用于 Kling 报告/论文排版的 LaTeX 模板。该模板结构化了文件目录，以确保编译顺利并保持样式统一。

## 📂 1. 文件结构说明

在使用之前，请先了解以下文件结构：

```text
Kling_report_template/
├── main.tex            <-- [核心文件] 您的论文主文件，请在此处进行编辑
├── paper.bib           <-- [参考文献] BibTeX 格式的参考文献数据
├── assets/             <-- [资源文件夹] 存放图片、图表等资源文件
│   └── ... (您的图片)
├── kling/              <-- [样式文件夹] 核心样式定义 (⚠️ 请勿修改)
│   ├── kling.cls       (文档类定义)
│   ├── klingai-black.png (Logo图片)
│   └── ...
└── README.md           <-- 本说明文件
```

-----

## 🛠️ 2. 如何使用

### ⚠️ 关键注意事项：`kling` 文件夹

* **请勿修改** `kling` 文件夹内的任何内容（包括 `.cls` 文件和 Logo 图片）。
* 文件夹包含了页眉、页脚、字体和排版的核心逻辑。主文件 `main.tex` 依赖于路径 `kling/kling` 来加载样式。移动或修改此文件夹可能导致编译报错。

### ✅ 资源管理：`assets` 文件夹

* **存放位置**：请将您论文中所有的图片资源（如 `.jpg`, `.png`, `.pdf`）放入 `assets` 文件夹中。
* **引用方式**：在 `main.tex` 中插入图片时，建议使用相对路径指向该文件夹。
  * *示例代码：*

        ```latex
        \includegraphics[width=\linewidth]{assets/your_image.pdf}
        ```

* 您可以自由添加、删除或替换 `assets` 文件夹中的内容。

-----

## 📝 3. 如何修改 `main.tex`

打开 `main.tex` 文件，根据您的需求修改以下部分：

### 3.1 基础信息配置

在文档的前言部分（Preamble），修改标题和页眉信息：

```latex
\title{此处填写您的论文标题}
\headertext{此处填写页眉显示的简短标题}
```

### 3.2 作者与单位

使用以下格式添加作者和归属单位：

```latex
% 作者信息：[编号]对应单位，*或\dag对应脚注
\author[1*]{Zhang San}
\author[2]{Li Si}

% 单位信息
\affiliation[1]{Kling AI Research}
\affiliation[2]{University Name}
```

### 3.3 摘要 (Abstract)

**注意**：本模板的摘要使用的是命令格式 `\abstract{...}`，而不是环境格式 `\begin{abstract}`。

```latex
\abstract{
    在此处撰写您的摘要内容。请保留花括号。
}
```

### 3.4 侧边栏元数据 (Metadata)

首页左下角的元数据框可以通过 `\metadata` 命令自定义：

```latex
\metadata[Data]{June 13, 2025}
\metadata[Code]{\url{https://github.com/your-repo}}
\metadata[Project Page]{\url{https://your-website.com}}
```

### 3.5 正文撰写

在 `\begin{document}` 之后撰写正文。您可以正常使用标准的 LaTeX 命令，例如：

* `\section{Introduction}`
* `\subsection{Methodology}`
* `\paragraph{Bold Paragraph Title}`

### 3.6 参考文献

1. 打开根目录下的 `paper.bib` 文件。
2. 将您的 BibTeX 引用数据粘贴进去（例如从 Google Scholar 复制的内容）。
3. 在 `main.tex` 中使用 `\cite{key}` 或 `\citep{key}` 进行引用。模板已配置好引用样式。