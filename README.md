# 兰州理工大学课程设计 LaTeX 模板

本项目用于课程设计报告排版，基于 [LuThesis](https://github.com/estivalinp/LuThesis) 修改而来。当前版本使用 `main.tex` 作为入口，并以 `sections/` 目录组织课程设计报告内容。

## 项目来源与致谢

- 本模板基于 LuThesis 修改。
- LuThesis 基于 ThuThesis v5.3.2 改编。
- 感谢原作者和相关开源模板贡献者。

请同时阅读 [NOTICE.md](NOTICE.md)，了解来源、版权和使用边界。

## 模板预览

模板编译效果可参考：[main.pdf](./main.pdf)。

## 使用方法

1. 修改 `sections/00_cover.tex` 中的封面信息、摘要和关键词。
2. 修改 `sections/` 下各章节文件，例如 `chap01.tex` 至 `chap05.tex`、`06_conclusion.tex`、`07_references.tex` 和 `08_appendixA.tex`。
3. 将图片放入 `figures/`，并在章节文件中通过 `\includegraphics` 引用；主文件已设置该目录为图片搜索路径。
4. 使用 XeLaTeX 编译 `main.tex`。

当前版本采用 `sections/` 目录；若使用其他基于上游版本整理的分支或副本，也可能使用 `data/` 目录。此时请修改对应章节文件，并同步检查 `main.tex` 的引用路径。

## 推荐编译方式

在本目录中执行：

```bash
latexmk -xelatex main.tex
```

或手动多次执行：

```bash
xelatex main.tex
xelatex main.tex
```

如果使用 BibTeX 文献库，还应在两次 XeLaTeX 之间执行相应的 BibTeX 命令。具体次数和顺序取决于参考文献方案。

## 项目结构

```text
.
├── main.tex                 # 报告主入口
├── sections/                # 封面、摘要、正文、参考文献和附录
├── figures/                 # 图片资源
├── fonts/                   # 模板使用的本地字体资源
├── thuthesis.cls            # 上游演变而来的文档类
├── thuthesis.cfg            # 文档类配置
├── thuthesis.sty            # 本地宏包扩展
├── algorithm2e.sty          # 算法排版宏包
├── .gitignore               # Git 忽略规则
├── README.md                # 使用说明
└── NOTICE.md                # 来源、版权与使用边界说明
```

## 常见问题

### 为什么引用显示 `??`

目录、交叉引用和参考文献需要多次编译才能稳定。优先使用 `latexmk -xelatex main.tex`；手动编译时至少再运行一次 XeLaTeX。若使用 BibTeX，还应检查 `.bib` 文件路径、引用键和编译顺序。

### 为什么图片找不到

请确认图片已放入 `figures/`，文件名大小写、扩展名与 `\includegraphics` 中的名称完全一致。不要随意删除 `main.tex` 中的 `\graphicspath{{figures/}}` 设置。

### 为什么中文字体报错

本模板应使用 XeLaTeX 编译。请确认 `fonts/` 下字体文件完整且未被移动或改名；如需按课程要求替换字体，请自行确认字体授权与最终排版效果。

### 为什么不要直接删除 `thuthesis.*` 文件

`thuthesis.cls`、`thuthesis.cfg` 和 `thuthesis.sty` 是模板的本地依赖，且保留了上游版权和许可证说明。删除或随意修改它们可能导致编译失败、格式变化或来源信息缺失。

## 发布说明

本模板仅用于课程设计报告排版学习和交流。使用者应根据自己课程、学院或指导教师的具体要求自行调整格式；模板不保证符合所有课程的提交规范。
