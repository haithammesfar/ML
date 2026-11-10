# Machine Learning – Kapitel 1: Cheat-Sheet

## 1. Einleitung
- **Machine Learning:** Muster aus Daten lernen, um neue Daten zu bearbeiten.
- **Mitchell:** Lernen aus Erfahrung **E** bei Aufgabe **T**, wenn Leistung gemäß **P** besser wird.
- Beispiel: E = gelabelte Katzen-/Hundebilder; T = Bildklassifikation; P = Genauigkeit auf neuen Bildern.
- **Training:** Parameter aus Daten lernen. **Anwendung:** Neue Eingaben vorhersagen. **Generalisierung:** Auf unbekannte Daten übertragen.
- **Überwacht:** Daten mit Labels; Klassifikation/Regression.
- **Unüberwacht:** Daten ohne Labels; z. B. Clustering.
- **Reinforcement Learning:** Aktionen und Belohnungen.
- **Deep Learning:** Tiefe neuronale Netze, in verschiedenen Lernarten einsetzbar.

## 2. Notation und O-Notation
- $\mathbb N=\{1,2,\dots\}$, $\mathbb N_0=\{0,1,\dots\}$, $\mathbb Z$ ganze Zahlen, $\mathbb R$ reelle Zahlen.
- $\mathbb R_{\ge0}$ enthält 0; $\mathbb R_{>0}$ nicht.
- **Multimenge:** Elemente dürfen mehrfach vorkommen.
- $g\in O(f)$, falls $\exists c>0, n_0:\forall n>n_0,\ g(n)\le cf(n)$.
- Beispiel: $3n^2+5n+7\in O(n^2)$.

## 3. Lineare Algebra
- **Vektor:** $x\in\mathbb R^n$, Spaltenvektor $(x_1,\dots,x_n)^T$.
- **Norm:** $\|x\|=\sqrt{\sum_i x_i^2}$; $\|(3,4)^T\|=5$.
- **Matrix:** $X\in\mathbb R^{n\times m}$: n Zeilen, m Spalten.
- **Transponierte:** $X^T\in\mathbb R^{m\times n}$.
- **Multiplikation:** $(n\times m)(m\times k)=(n\times k)$.
- **Skalarprodukt:** $x^Ty=\sum_i x_i y_i$ (Zahl).
- **Äußeres Produkt:** $xy^T$ (Matrix).
- **Einheitsmatrix:** $IX=XI=X$.
- **Inverse:** $XX^{-1}=I$ (falls vorhanden).
- **Symmetrisch:** $X=X^T$.
- **Positiv definit (symmetrisch):** $x^TXx>0$ für alle $x\ne0$.
- **Determinante 2×2:** $\det\begin{pmatrix}a&b\\c&d\end{pmatrix}=ad-bc$.
- **Invertierbarkeit:** $\det X\ne0$.
- **Eigenwert/-vektor:** $Xv=\lambda v$, $v\ne0$; $\det(X-\lambda I)=0$.
- **Linearkombination:** $w=\sum_i\alpha_i v_i$.
- **Linear unabhängig:** Kein Vektor ist Linearkombination der anderen.
- **Basis von $\mathbb R^n$:** n linear unabhängige Vektoren.
- **Orthogonal:** $v^Tw=0$; **orthonormal:** zusätzlich $\|v\|=1$.

## 4. Analysis
- **Ableitung:** $f(x)=x^2\Rightarrow f'(x)=2x$.
- **Partielle Ableitung:** Ableitung nach einer Variablen, andere konstant.
- **Gradient:** $\nabla f=(\partial f/\partial x_1,\dots,\partial f/\partial x_n)^T$.
- Beispiel: $f(x,y)=x^2+3y^2\Rightarrow\nabla f=(2x,6y)^T$.

## 5. Optimierung
- **Minimierung:** $\min_x f(x)$.
- **Gradient Descent:** $x_i=x_{i-1}-\gamma\nabla f(x_{i-1})$, Lernrate $\gamma>0$.
- Kleine Lernrate: oft langsam; zu große: Überschwingen/Instabilität möglich.
- Konvergenz nur unter geeigneten Voraussetzungen; stationärer Punkt nicht immer globales Minimum.
- **Nebenbedingung:** $\min f(x)$ sodass $x\in X$.
- Beispiel: $\min(x_1^2+x_2^2)$ sodass $x_1+x_2=2$ → $(1,1)$, Minimum 2.
- **Quadratischer Strafterm im Skript:** $f(x)+\lambda h(x)^2$ für Nebenbedingung $h(x)=0$; große $\lambda$ erzwingt näherungsweise Einhaltung.

## 6. Stochastik
- **Mittelwert:** $\tilde x=\frac1n\sum_i x_i$.
- **Varianz (Grundgesamtheit):** $\sigma^2=\frac1n\sum_i(x_i-\tilde x)^2$.
- **Standardabweichung:** $\sigma=\sqrt{\sigma^2}$.
- **Wahrscheinlichkeit:** $P(\Omega)=1$; für disjunkte A,B gilt $P(A\cup B)=P(A)+P(B)$.
- **Bedingte Wahrscheinlichkeit:** $P(A\mid B)=\frac{P(A\cap B)}{P(B)}$ für $P(B)>0$.
- **Gleichverteilung:** $P_0(A)=|A|/|\Omega|$ bei endlichem $\Omega$.
- **Dichte:** $p(x)\ge0$, $\int_{-\infty}^{\infty}p(x)\,dx=1$.
- **Normalverteilung:** $\mathcal N(\mu,\sigma^2)$ mit $p(x)=\frac1{\sqrt{2\pi\sigma^2}}e^{-(x-\mu)^2/(2\sigma^2)}$.

## Häufige Prüfungsfallen
1. $x^Ty$ ist eine Zahl, $xy^T$ eine Matrix.
2. Matrixmultiplikation ist im Allgemeinen nicht kommutativ: $XY\ne YX$.
3. $\sigma$ (Standardabweichung) ist nicht $\sigma^2$ (Varianz).
4. $P(A\mid B)$ ist im Allgemeinen nicht $P(B\mid A)$.
5. Big-O ist eine asymptotische obere Schranke, keine exakte Laufzeit.
6. Deep Learning ist keine eigenständige vierte Kategorie der Einteilung nach Erfahrung E.
