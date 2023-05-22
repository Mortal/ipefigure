Ipe in LaTeX example
====================

The example document mydoc.tex uses memoir with 12pt Libertine font.

In Ipe, the Libertine font is configured with the same line as in the LaTeX preamble:

`\usepackage{libertine}`

In Ipe, to configure the 12pt font, add this in the preamble (Ctrl-Shift-P):

```
\makeatletter
\input{size12.clo}
\makeatother
```

This uses the article.cls way of setting font sizes, which is compatible with how memoir does it.

To create a precise box in Ipe, change 100 to whatever size you want (in points `pt`) in the following text, then copy it with Ctrl-C and paste it into Ipe with Ctrl-V:

```
<ipeselection pos="0 0">
<path>
0 0 m
0 100 l
100 100 l
100 0 l
h
</path>
</ipeselection>
```

If you use multiple views in Ipe, this turns into multiple pages in the PDF, which you can include into LaTeX with the argument `\includegraphics[page=N]`.

To avoid extra horizontal space in the LaTeX layout (which will turn into "overfull hbox" warnings), use `%` at the ends of lines. See mydoc.tex for an example.

Don't use `width=\textwidth` or similar in LaTeX! Instead, measure up how much space in the document you have, and then size your Ipe figure accordingly.
This allows you to use the same font size in the figure as you have in the rest of the document.
