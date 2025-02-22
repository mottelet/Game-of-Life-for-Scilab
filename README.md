# Conway's Game of Life

[![DOI](https://zenodo.org/badge/576362494.svg)](https://zenodo.org/badge/latestdoi/576362494)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/aumpierre-unb/Game-of-Life-for-Scilab)

![Illustrative graphical output](docs/ezgif.com-gif-maker.gif)

## Install and load `game_of_life` package for Scilab

1\. Download `v0.1.3.zip` file from the current release page.

2\. Set Scilab current directory to the download folder.

3\. To install and load `v0.1.3.zip` type:

```dotnetcli
atomsInstall('v0.1.3.zip'),..
atomsLoad('conway')
```

## Citation of `game_of_life`

You can cite all versions (both released and pre-released), by using
[DOI 105281/zenodo.7420301](https://doi.org/10.5281/zenodo.7420301).
This DOI represents all versions, and will always resolve to the latest one.

<!--To cite the last released version, please check
https://zenodo.org/account/settings/github/repository/aumpierre-unb/Game-of-Life-for-Scilab.-->

---

## The Conway's Game of Life

Conway's Game of Life computes the configuration of the next generation of a grid of square cells, each of which is in either live or dead. Each cell will be live or dead in the next generation according to two simple rules:

- A live cells with exactly 2 or 3 live neighbors stays a live cell, otherwise it dies.
- A dead cell with 3 live neighbors becomes alive, otherwise is stays dead.

As simple as these rules may be, they can result in surprising complexity from relatively simple initial configurations.

## The `game_of_life` Package

`game_of_life` provides the following functions:

- `genzero`
- `conway`
- `evolution`

### `genzero`

`genzero` generates a matrix of ones and zeros of m lines and n columns.

If probability for live cell if given, the values of individual cells are computed accordingly.

If the grid pattern is assigned by strings 'block', 'glider', 'blinker', 'toad' or 'beacon' matrix is generated with the pattern at its superior left corner.

**Syntax:**

```dotnetcli
[A]=genzero(m,n,P)
```

**Examples:**

Generate a spaceship glider pattern in a 9 lines and 7 columns matrix.

```dotnetcli
A=genzero(9,7,'glider')
```

Generate a 27 by 28 cells grid where individual cells have a 26:74 chance to be live or dead.

```dotnetcli
A=genzero(27,28,.26)
```

### `conway`

`conway` computes the configuration of the next generation of a grid of square cells, each of which is in either live or dead.

Each cell will be live or dead in the next generation according to the rules of the Conway's game of life:

- A live cells with exactly 2 or 3 live neighbors stays a live cell, otherwise it dies.
- A dead cell with 3 live neighbors becomes alive, otherwise is stays dead.

**Syntax:**

```dotnetcli
[B]=conway(A,cyc,fig)
```

**Examples:**

Compute the next generation of a spaceship glider pattern in a 10 by 10 cells grid and visualize the grids on plots.

```dotnetcli
A=genzero(10,10,'glider');..
B=conway(A,%t,%t)
```

### `evolution`

`evolution` computes the evolution of a grid of square cells according to the rules of the Conway's game of life.

The computation will be interrupted if the grid comes to a stable configuration (including death of all cells).

**Syntax:**

```dotnetcli
[B]=evolution(A,N,cyc,fig)
```

**Examples:**

Observe the evolution of the first 200 generations of a grid originally set as a spaceship glider pattern in a periodic 13 by 11 cells grid.

```dotnetcli
A=genzero(13,11,'glider');..
B=evolution(A,200,%t,%t)
```

Generate a periodic 27 by 28 cells grid where individual cells have a 26:74 chance to be live or dead and observe its evolution.

```dotnetcli
A=genzero(27,28,.26);..
B=evolution(A,%inf,%t,%t)
```

Copyright &copy; 2022 2023 Alexandre Umpierre

email: aumpierre@gmail.com
