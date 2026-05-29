# HIT Undergraduate Thesis LaTeX Template

<p align="center">
  <strong>哈尔滨工业大学本科毕业论文（设计）LaTeX 模板整理版</strong>
</p>

<p align="center">
  <a href="https://github.com/HIT-JimmyXiao/HIT-Undergraduate-Thesis-LaTeX-Template"><img alt="Repository" src="https://img.shields.io/badge/GitHub-HIT--Undergraduate--Thesis--LaTeX--Template-181717?logo=github"></a>
  <img alt="TeX Live" src="https://img.shields.io/badge/TeX%20Live-XeLaTeX-008080?logo=latex">
  <img alt="HIT" src="https://img.shields.io/badge/HIT-Undergraduate%20Thesis-1f4f8f">
  <img alt="Status" src="https://img.shields.io/badge/Status-Word%20example%20aligned-success">
</p>

本项目是在 [hithesis/hithesis](https://github.com/hithesis/hithesis) 基础上整理的哈尔滨工业大学本科毕业论文（设计）LaTeX 模板，面向哈尔滨校区本科毕设写作场景。当前版本重点对齐新版《本科毕业论文（设计）书写范例（理工类）》的视觉习惯，保留 `hithesis` 的核心类文件、参考文献样式和封面生成逻辑，并对本科生常用排版细节做了默认化处理。

维护者：`HIT_Jimmy`  
联系邮箱：`2023112881@stu.hit.edu.cn`

## 项目定位

这个仓库适合希望用 LaTeX 完成哈工大本科毕业论文（设计）的同学使用。它不是从零重写的模板，而是一个面向本科毕设场景的可编译整理版：

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

Overleaf 用户可以直接上传整个项目目录，并将主文件设置为 `thesis.tex`，编译器选择 `XeLaTeX`。

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

- `thesis.tex` 默认设置为 `fontset=windows,type=bachelor,campus=harbin`。
- 长表格默认字号为五号，并将 `longtable` 行距调整为更接近 Word 范例的视觉密度。
- 表格列建议采用“短字段居中、长说明左对齐”的原则，避免编号、数值、方向、置信区间等字段偏左。
- 参考文献条目间距保持紧凑，避免本科论文末尾参考文献页出现异常松散。
- 本科示例默认关闭“攻读学士学位期间取得创新性成果”页，减少与新版书写范例不一致的默认输出。

## 编译注意

- Windows 本地建议保留 `fontset=windows`；如果在 Linux 或 Overleaf 编译，可尝试切换为 `fontset=fandol` 或根据平台安装中文字体。
- 图片建议优先使用 PDF、EPS 或高分辨率 PNG，并放入 `figures/`。
- 参考文献改动后需要运行 BibTeX 或使用 `latexmk -xelatex` 自动处理。
- 不建议提交 `.aux`、`.log`、`.toc`、`.out`、`.bbl`、`.blg` 等编译生成文件。

## Git 提交流程

如果你已经在 GitHub 创建了空仓库，可以在本目录执行：

```powershell
git init
git add .
git commit -m "Initial release: HIT undergraduate thesis LaTeX template"
git branch -M main
git remote add origin https://github.com/HIT-JimmyXiao/HIT-Undergraduate-Thesis-LaTeX-Template.git
git push -u origin main
```

如果远程仓库已经有内容，先执行：

```powershell
git remote add origin https://github.com/HIT-JimmyXiao/HIT-Undergraduate-Thesis-LaTeX-Template.git
git pull origin main --allow-unrelated-histories
git add .
git commit -m "Add HIT undergraduate thesis LaTeX template"
git push -u origin main
```

## 致谢

本项目基于 [hithesis/hithesis](https://github.com/hithesis/hithesis) 整理和再配置。`hithesis` 为哈尔滨工业大学 LaTeX 学位论文模板提供了核心文档类、封面逻辑、参考文献样式和大量规范适配工作。感谢原项目作者和维护者的长期贡献。

## 许可证说明

本仓库中来自 `hithesis` 的文件遵循其上游许可证说明。原项目声明代码文件可按 LaTeX Project Public License 分发或修改，同时文档内容涉及 CC BY-NC 4.0 授权。使用、分发或二次修改前，请同时阅读本仓库的 `NOTICE.md` 和上游项目许可证说明。
