# Chatty — Póster SEPLN 2026

Fuentes LaTeX del póster **"Chatty: A Tool for Building and Evaluating Customizable LLM Assistants"**,
presentado en **SEPLN 2026**.

Manuel Couto-Pintos, Marcos Fernández-Pichel, Mario Ezra Aragón, David Gallego-Conde y David E. Losada
— Centro Singular de Investigación en Tecnoloxías Intelixentes (CiTIUS), Universidade de Santiago de Compostela (USC), España.

## Vista previa

El PDF compilado está en [`poster.pdf`](poster.pdf) (A0, vertical).

## Contenido del repositorio

| Archivo | Descripción |
| --- | --- |
| `poster.tex` | Documento principal del póster |
| `poster.pdf` | PDF compilado (A0 vertical) |
| `baposter.cls` | Clase de póster `baposter` |
| `*.sty` | Paquetes locales (`multirow`, `soul`, `svg`, `wrapfig`) |
| `figures/` | Figuras, gráficas, logos institucionales y de financiación, y códigos QR |

## Compilación

Requiere una distribución TeX Live razonablemente completa (`texlive-latex-extra`, `tcolorbox`, `pgf/tikz`).

```bash
latexmk -pdf poster.tex
```

`baposter` coloca las cajas con coordenadas TikZ (`remember picture`), así que hacen **falta dos pasadas**:
con `pdflatex` a secas hay que ejecutarlo dos veces o las cajas se solapan. Overleaf usa `latexmk`, así que
allí funciona sin más.

Las figuras se resuelven mediante `\graphicspath{{figures/}}`, así que hay que compilar desde la raíz del repositorio.

> Nota: la compilación emite un aviso no bloqueante (`There's no line here to end`) procedente de la
> construcción de la cabecera de `baposter`. El PDF se genera igualmente.

## Abrir en Overleaf

[![Open in Overleaf](https://img.shields.io/badge/Open%20in-Overleaf-47A141?logo=overleaf&logoColor=white)](https://www.overleaf.com/docs?snip_uri=https://github.com/manucouto1/SEPLN2026-poster-chatty/archive/refs/heads/main.zip&engine=pdflatex)

También se puede descargar el repositorio como ZIP e importarlo desde *New Project → Upload Project*.

## Financiación

El póster incluye al pie los logos de las entidades financiadoras: Ministerio de Ciencia, Innovación y
Universidades / Agencia Estatal de Investigación (cofinanciado por la Unión Europea), Xunta de Galicia
(Consellería de Cultura, Educación e Universidade) y la Cátedra CAMELIA (USC-Plexus de IA aplicada a la
Medicina Personalizada de Precisión).

Los tamaños de esa banda se controlan con `\FundWA` / `\FundWB` / `\FundWC` / `\FundGap`, definidos al
principio de `poster.tex`. Se expresan como fracciones de `\linewidth` a propósito: `baposter` compone la
página a `fontscale=0.31` y la escala x3.23, así que una longitud en `cm` dentro del cuerpo **no** es la
del A0 impreso.

## Licencia

Contenido del póster © los autores. El resto de archivos `.cls`/`.sty` conserva la licencia original de sus
respectivos autores (LPPL).
