# HIT Undergraduate Thesis LaTeX Template

<p align="center">
  <strong>哈尔滨工业大学本科毕业论文（设计）LaTeX 模板整理版</strong>
</p>

<p align="center">
  <em>A clean, reproducible and HIT-style LaTeX template for undergraduate thesis writing.</em>
</p>

<p align="center">
  <a href="https://github.com/HIT-JimmyXiao/HIT-Undergraduate-Thesis-LaTeX-Template">
    <img alt="GitHub Repository" src="https://img.shields.io/badge/GitHub-HIT--Undergraduate--Thesis--LaTeX--Template-181717?logo=github">
  </a>
  <img alt="TeX Live" src="https://img.shields.io/badge/TeX%20Live-XeLaTeX-008080?logo=latex">
  <img alt="HIT" src="https://img.shields.io/badge/HIT-Undergraduate%20Thesis-1f4f8f">
  <img alt="Template Status" src="https://img.shields.io/badge/Status-Format%20Aligned-success">
  <img alt="Maintainer" src="https://img.shields.io/badge/Maintainer-HIT--Jimmy-blueviolet">
</p>

---

## Overview

本项目是在 [hithesis/hithesis](https://github.com/hithesis/hithesis) 基础上整理的 **哈尔滨工业大学本科毕业论文（设计）LaTeX 模板**，面向哈尔滨校区本科毕业论文、毕业设计和课程论文式长文档写作场景。

当前版本重点参考新版《本科毕业论文（设计）书写范例（理工类）》的版式习惯，对本科生最常遇到的封面、扉页、摘要、目录、图表、公式、参考文献和附录排版进行了整理与默认化配置，在尽量保留 `hithesis` 核心类文件、参考文献样式和封面生成逻辑的基础上，使模板更适合直接写作、修改和提交。

## Features

- **HIT-style layout**：对齐哈尔滨工业大学本科毕业论文（设计）常用版式习惯；
- **XeLaTeX workflow**：基于 TeX Live / XeLaTeX，适合中文论文排版；
- **Structured thesis writing**：支持封面、扉页、摘要、目录、正文、参考文献、声明页、致谢和附录；
- **Clean visual defaults**：优化中英文混排、图题表题、页眉页脚和常见浮动体显示；
- **Reproducible writing pipeline**：适合本科毕设、科研训练、课程论文和模板二次开发。

## Maintainer

本模板由 **HIT_Jimmy** 整理维护。维护者本科背景为 **哈尔滨工业大学大数据管理与应用**，后续研究方向聚焦于数据科学、人工智能与交叉学科应用。

- Email: `2023112881@stu.hit.edu.cn`
- Repository: [HIT-Undergraduate-Thesis-LaTeX-Template](https://github.com/HIT-JimmyXiao/HIT-Undergraduate-Thesis-LaTeX-Template)

## Acknowledgement

本项目基于 [hithesis/hithesis](https://github.com/hithesis/hithesis) 进行整理与适配。感谢原项目作者和社区对哈尔滨工业大学 LaTeX 论文模板生态的长期贡献。
## 项目定位

这个仓库适合希望用 LaTeX 完成哈工大本科毕业论文（设计）的同学使用，一个面向本科毕设场景的可编译整理版：

- 默认使用 `type=bachelor,campus=harbin`，适配哈尔滨校区本科论文。
- 默认使用 Windows 字体集，贴近学校 Word 范例的宋体/黑体环境。
- 默认不编译“攻读学士学位期间取得创新性成果”页；如学院另有要求，可在 `thesis.tex` 中取消对应注释。
- 优化正文行距、参考文献间距、长表格行距和表格短字段居中显示。
- 保留 `hithesis` 原始宏包结构，便于继续按官方模板选项扩展。

## 快速开始

推荐使用 TeX Live 2024 或更新版本，并使用 `XeLaTeX` 编译。

```powershell
git clone https://github.com/HIT-JimmyXiao/HIT-Undergraduate-Thesis-LaTeX-Template.git
cd HIT-Undergraduate-Thesis-LaTeX-Template
latexmk -xelatex thesis.tex
```

如果没有配置 `latexmk`，可以直接运行：

```powershell
xelatex thesis.tex
bibtex thesis
xelatex thesis.tex
xelatex thesis.tex
```

Overleaf 用户可以直接上传整个项目目录，并将主文件设置为 `main.tex` 或 `thesis.tex`，编译器选择 `XeLaTeX`。当前入口文件会自动检测 Windows 中易字体；若检测不到，则自动切换到 `fontset=fandol`，避免 Overleaf 上出现 `SimSun/SimHei/KaiTi/FangSong` 缺字报错。

## 目录结构

```text
HIT-Undergraduate-Thesis-LaTeX-Template/
├── thesis.tex                  # 主文件：论文结构、章节引入、模板选项
├── front/
│   ├── cover.tex               # 封面与题名页信息
│   └── denotation.tex          # 符号表/缩略语表
├── body/
│   └── bachelor_sample.tex     # 本科论文正文示例
├── back/
│   ├── conclusion.tex          # 结论
│   ├── acknowledgements.tex    # 致谢
│   ├── publications.tex        # 创新性成果页，可选启用
│   └── appendix01.tex          # 附录示例
├── figures/
│   └── empty-resolution.pdf    # 示例图片占位文件
├── hithesisbook.cls            # 核心文档类
├── hithesisbook.cfg            # 中文标题、封面、声明等配置
├── hithesis.sty                # 常用宏包与扩展命令
├── hithesis.bst                # 参考文献样式
├── reference.bib               # BibTeX 示例库
├── latexmkrc                   # latexmk 编译配置
└── Makefile                    # make 编译入口
```

## 常用修改位置

| 修改目标 | 文件 | 说明 |
| --- | --- | --- |
| 论文题目、作者、导师、学院、专业 | `front/cover.tex` | 封面和扉页信息集中在这里 |
| 摘要、关键词、目录前内容 | `front/cover.tex`、`front/denotation.tex` | 按示例替换即可 |
| 正文章节 | `body/bachelor_sample.tex` 或新增章节文件 | 可在 `thesis.tex` 中用 `\include{}` 引入 |
| 参考文献 | `reference.bib` | 使用 BibTeX，样式为 `hithesis` |
| 致谢、结论、附录 | `back/` | 按需保留或拆分 |
| 创新性成果页 | `thesis.tex`、`back/publications.tex` | 默认关闭，如需使用请取消注释 |

## 本整理版的排版调整

与原始 `hithesis` 示例相比，本整理版重点做了以下本科毕设友好调整：

- `thesis.tex` 默认优先使用 `fontset=windows,type=bachelor,campus=harbin`；若系统中不存在 Windows 中易字体，则自动回退到 `fontset=fandol`，便于 Overleaf 直接编译。
- 新增 `main.tex` 轻量入口文件，兼容 Overleaf 默认以 `main.tex` 作为主文件的用法。
- 目录中“第1章  绪论”类章标题条目取消原有固定宽编号盒，编号与标题之间仅保留约两个半角空格。
- 哈尔滨本科二级标题和三级标题上下间距按正文半行距设置，即前后各 `10.25197bp`。
- 公式示例不在公式上方额外留空白段落，避免 Word 范例中不存在的空行感。
- 对“（1）标题。    正文”这类编号说明段，可使用 `\hititemparagraph{（1）标题。}{正文内容。}`，保证编号标题为黑体、空格后正文保持正常宋体，且间隔为 4 个汉字宽度。
- 长表格默认字号为五号，并将 `longtable` 行距调整为更接近 Word 范例的视觉密度。
- 表格列建议采用“短字段居中、长说明左对齐”的原则，避免编号、数值、方向、置信区间等字段偏左。
- 参考文献条目间距保持紧凑，避免本科论文末尾参考文献页出现异常松散。
- 本科示例默认关闭“攻读学士学位期间取得创新性成果”页，减少与新版书写范例不一致的默认输出。

## 编译注意

- Windows 本地会自动使用 `fontset=windows`；Linux 或 Overleaf 若无中易字体，将自动回退到 `fontset=fandol`，一般不需要手动改入口文件。若平台默认寻找 `main.tex`，可直接以仓库内新增的 `main.tex` 作为主文件。
- 图片建议优先使用 PDF、EPS 或高分辨率 PNG，并放入 `figures/`。
- 参考文献改动后需要运行 BibTeX 或使用 `latexmk -xelatex` 自动处理。
- 不建议提交 `.aux`、`.log`、`.toc`、`.out`、`.bbl`、`.blg` 等编译生成文件。



## 致谢

本项目基于 [hithesis/hithesis](https://github.com/hithesis/hithesis) 整理和再配置。`hithesis` 为哈尔滨工业大学 LaTeX 学位论文模板提供了核心文档类、封面逻辑、参考文献样式和大量规范适配工作。感谢原项目作者和维护者的长期贡献。

## 许可证说明

本仓库中来自 `hithesis` 的文件遵循其上游许可证说明。原项目声明代码文件可按 LaTeX Project Public License 分发或修改，同时文档内容涉及 CC BY-NC 4.0 授权。使用、分发或二次修改前，请同时阅读本仓库的 `NOTICE.md` 和上游项目许可证说明。
