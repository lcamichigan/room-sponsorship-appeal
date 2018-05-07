# Room Sponsorship Appeal

[![Build status](https://ci.appveyor.com/api/projects/status/m487el1pt3uar2yo?svg=true)](https://ci.appveyor.com/project/lcamichigan/room-sponsorship-appeal)

This is a collection of resources for an appeal to sponsor personalized plaques
on doors of Sigma’s chapter house.

## Contents

* [Getting Started](#getting-started)
* [Creating an InDesign File](#creating-an-indesign-file)
* [About the Letter](#about-the-letter)

## Getting Started

To edit the letter about the plaques, you need:

* [Adobe InDesign](https://www.adobe.com/products/indesign.html). Visit
  https://www.adobe.com/creativecloud/plans.html for more information.

* Letter.idml. The easiest way to get this file is to download it from
  https://ci.appveyor.com/project/lcamichigan/room-sponsorship-appeal/build/artifacts,
  but you can also [create your own](#creating-an-indesign-file).

* These fonts:

  | Font                                                             | Download URL                                                        |
  |------------------------------------------------------------------|---------------------------------------------------------------------|
  | [Gillius](http://arkandis.tuxfamily.org/adffonts.html)           | http://arkandis.tuxfamily.org/fonts/Gillius-Collection-20110312.zip |
  | [Linux Libertine](http://libertine-fonts.org) (OpenType version) | http://mirrors.ctan.org/fonts/libertine.zip                         |

## Creating an InDesign File

Creating an InDesign IDML file from the files in this repository requires the
free [Zip](http://www.info-zip.org/Zip.html) utility. To install Zip on Windows:

1. Click ftp://ftp.info-zip.org/pub/infozip/win32/zip300xn-x64.zip to download
   zip300xn-x64.zip.

2. Right-click zip300xn-x64.zip, choose Extract All, and then click Extract to
   extract a folder named zip300xn-x64.

3. Right-click zip300xn-x64.zip in the zip300xn-x64 folder you just extracted,
   choose Extract All, and then click Extract to extract another folder named
   zip300xn-x64.

4. Move this second zip300xn-x64 folder to C:\Program Files.

Zip is included with macOS.

To create an InDesign file, first download this repository as a ZIP archive. To
do this, click
[here](https://github.com/lcamichigan/room-sponsorship-appeal/archive/master.zip).
Unzip the archive wherever you wish. Then, `cd` to the
[Letter IDML](Letter%20IDML) folder and enter in PowerShell

```powershell
& "$env:ProgramFiles\zip300xn-x64\zip" -X0 ..\Letter.idml mimetype
& "$env:ProgramFiles\zip300xn-x64\zip" --recurse-paths --no-dir-entries -X9 ..\Letter.idml * --exclude mimetype
```

or in Command Prompt

```batch
"%ProgramFiles%\zip300xn-x64\zip" -X0 ..\Letter.idml mimetype
"%ProgramFiles%\zip300xn-x64\zip" --recurse-paths --no-dir-entries -X9 ..\Letter.idml * --exclude mimetype
```

or in Terminal

```sh
zip -X0 ../Letter.idml mimetype
zip --recurse-paths --no-dir-entries -X9 ../Letter.idml * --exclude *.DS_Store mimetype
```

## About the Letter

The letter includes an embedded image of a cross and crescent created using a
[cross-and-crescent package](https://github.com/lcamichigan/cross-and-crescent)
in LaTeX. To create this image,
[install](https://github.com/lcamichigan/cross-and-crescent#installing) the
cross-and-crescent package, and then enter in PowerShell or Terminal

```sh
latex -jobname logo -output-format pdf '\documentclass{standalone}\usepackage{cross-and-crescent}\begin{document}\begin{tikzpicture}[scale=36bp/8cm]\crossAndCrescentSetMacros\draw[line join=round,line width=1bp]\crossAndCrescentPath\end{tikzpicture}\end{document}'
```
