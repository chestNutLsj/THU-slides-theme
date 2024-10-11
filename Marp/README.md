## 介绍

使用 PowerPoint 来制作组会 Slides 有点像大炮打蚊子，而且与自己的笔记脱节，每做一次 Slides 都要重新编写，非常麻烦。而使用 Marp 复用平时的 Markdown 笔记，则可以快速地做出 Slides 。

## 使用方法

看 `Marp/templates/` 目录下的样例 `demo01.md` 等文件，结合源代码观察生成的PDF，然后再自己尝试修改即可，非常容易上手。

好处:

1. Markdown语法,复制黏贴笔记就行了
2. 打公式方便
3. 排版比 Latex 模板更方便

BUG:

1. 导出 PDF 的时候记得先关掉预览
2. 实在导不出,用 terminal 命令导出 html,再用浏览器转 PDF(其实直接用 html 也行...)

### 导出命令

导出 html : `marp Slides.md`
导出 PDF : `marp Slides.md --pdf`
