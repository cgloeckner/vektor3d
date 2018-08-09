# vektor3d
LaTeX / TikZ extension for showing 3D vectors

The commands are named in German to avoid confusion with predefined LaTeX- and TikZ-commands.

## Example:

Either in plain LaTeX or within a TeX-area inside LyX:

```
\input{vectors.tikz}

\begin{tikzpicture}
	\achsen{0}{4.5}{0}{4.5}{0}{5.5};

	\punkt{P}{1}{4}{-2}{right};
	\punkt{Q}{3}{1}{0}{left};
	\vektor{$\vec{v}$}{P}{Q}{pos=0.5, above};

	\punkt{A}{3}{4}{4}{right};
	\punkt{B}{5}{1}{6}{left};
	\vektor{$\vec{v}$}{A}{B}{pos=0.5, above};
\end{tikzpicture}
```
