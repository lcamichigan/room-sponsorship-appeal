# Room Sponsorship Appeal

[![Build status](https://ci.appveyor.com/api/projects/status/m487el1pt3uar2yo?svg=true)](https://ci.appveyor.com/project/lcamichigan/room-sponsorship-appeal)

This is a collection of resources for an appeal to sponsor personalized plaques
on doors of Sigma’s chapter house.

## Contents

* [Getting Started](#getting-started)
* [About the Letter](#about-the-letter)

## Getting Started

To edit the letter about the plaques, you need:

* [Adobe InDesign](https://www.adobe.com/products/indesign.html). Visit
  https://www.adobe.com/creativecloud/plans.html for more information.

* Letter.idml. The easiest way to get this file is to download it from
  https://ci.appveyor.com/project/lcamichigan/room-sponsorship-appeal/build/artifacts,
  but you can also [create your own](https://github.com/lcamichigan/make-idml).

* These fonts:

  | Font                                                         | Download URL                                                        |
  |--------------------------------------------------------------|---------------------------------------------------------------------|
  | [Gillius](http://arkandis.tuxfamily.org/adffonts.html)       | http://arkandis.tuxfamily.org/fonts/Gillius-Collection-20110312.zip |
  | [Libertinus](https://github.com/libertinus-fonts/libertinus) | https://github.com/libertinus-fonts/libertinus/releases/latest      |

## About the Letter

The letter includes an embedded image of a cross and crescent created using a
[cross-and-crescent package](https://github.com/lcamichigan/cross-and-crescent)
in LaTeX. To create this image,
[install](https://github.com/lcamichigan/cross-and-crescent#installing) the
cross-and-crescent package, and then enter in PowerShell or Terminal

```sh
pdflatex -jobname logo '\documentclass{standalone}\usepackage{cross-and-crescent}\begin{document}\begin{tikzpicture}[scale=36bp/8cm]\crossAndCrescentSetMacros\draw[line join=round,line width=1bp]\crossAndCrescentPath\end{tikzpicture}\end{document}'
```
