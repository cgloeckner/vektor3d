# vektor3d
LaTeX / TikZ extension for showing 3D vectors. Just download the `vectors.tikz` and try out the examples below.

```
\usepackage{tikz}
\usetikzlibrary{decorations.markings}
```

Note, that the commands are named in German to avoid confusion with predefined LaTeX- and TikZ-commands. This won't change in future because I'm lazy :D

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
or
```
\input{vectors.tikz}

\begin{tikzpicture}
	\achsen{0}{6.5}{0}{9.5}{0}{4.5};

	\punkt{A}{6}{3}{0}{left};
	\punkt{B}{6}{9}{0}{right};
	\punkt{C}{2}{9}{0}{right};
	\punkt{D}{2}{3}{0}{left};
	\punkt{S}{4}{4.5}{4}{above};

	\draw (A) to (B) to (C);
	\draw[dashed] (A) to (D) to (C);

	\draw (A) to (S);
	\draw (B) to (S);
	\draw (C) to (S);
	\draw (D) to (S);
\end{tikzpicture}
```
or
```
\input{vectors.tikz}

\begin{tikzpicture}[scale=0.6]
	\achsen{-1.5}{6.5}{-1.5}{8.5}{-1.5}{2.5};

	\punkt{A}{6}{3}{0}{left};
	\punkt{B}{6}{9}{0}{right};
	\punkt{C}{2}{9}{0}{right};
	\punkt{D}{2}{3}{0}{left};
	\punkt{S}{4}{6}{4}{above};

	\punkt{M_1}{4}{9}{0}{right};
	\punkt{M_2}{4}{3}{0}{left};

	\draw (A) to (B) to (C);
	\draw[dashed] (A) to (D) to (C);

	\draw (A) to (S);
	\draw (B) to (S);
	\draw (C) to (S);
	\draw (D) to (S);

	\draw[red] (S) to (M_1) to (M_2);
	\draw pic["$\gamma$", draw] {angle=S--M_1--M_2};
\end{tikzpicture}
```
or
```
\begin{tikzpicture}[scale=0.5]
	%\achsen{-1.5}{3.5}{-1.5}{3.5}{-1.5}{3.5};

	\punkt{A}{12}{-3}{-3}{left};
	\punkt{B}{9}{9}{0}{right};
	\punkt{C}{9}{0}{9}{above};
	\punkt{S}{15}{3}{3}{left};

	\punkt{P}{8}{7}{7}{above};
	\punkt{Q}{4}{14}{11}{below};

	% clip required to limit line to the scene
	\clip (-12, -10) rectangle (15, 10);
	\gerade{P}{Q}{3};

	\draw (A) to (B) to (C) to cycle;
	\draw[dashed] (A) to (S) to (C);
	\draw[dashed] (B) to (S);
\end{tikzpicture}
```
