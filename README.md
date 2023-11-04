---
layout: default
title: circle-flags
---
# circle-flags <img src="logo.svg" alt="circle-flags animated logo" align="right">

A collection of ~~circular~~ ~~square~~ circular SVG country flags, based on
[square-flags][square-flags], in turn based on [circle-flags][circle-flags], by
HatScripts.

## Why a fork? What’s different?

In the process of creating the [square-flags][square-flags] flag set to provide
square variants to those provided by the original [circle-flags][circle-flags]
repo, with adjustments to better fit the square format, I ended up making
numerous further improvements to the original artwork in a number of places, and
adjustments to colours to provide better contrast, more accurately reflect the
source flag and so on.

It seemed to me the natural thing to do would be to ‘port back’ those
improvements to the circular format, and so I’ve created a [figma
file][circle-flags-figma] where I can maintain these alterations. This repo
might potentially be merged back in with the original, but in the meantime I’m
making my versions available here.

I’ve also added a small number of other flags to the project (as with
square-flags) which may or may not be interesting to you.

## Usage

```text
https://kapowaz.github.io/circle-flags/flags/xx.svg
```

(Where `xx` is the [ISO 3166-1 alpha-2 code][iso-3166-1] of a country).

For example, the following code:

```html
<img src="https://kapowaz.github.io/circle-flags/flags/br.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/cn.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/gb.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/id.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/in.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/ng.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/ru.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/us.svg" width="48">
```

...produces this:<br/><br/>
<img src="https://kapowaz.github.io/circle-flags/flags/br.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/cn.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/gb.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/id.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/in.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/ng.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/ru.svg" width="48">
<img src="https://kapowaz.github.io/circle-flags/flags/us.svg" width="48">

To view all the available flags, check [the gallery][gallery].

### NPM

If you want to install this package as a dependency, you can install it from
this GitHub repository:

```sh
npm install --save https://github.com/kapowaz/circle-flags
```

## Contributing

The design files for this set of flags can be found on [Figma as part of the
Circle Flags shared library][circle-flags-figma]. If you wish to make a
contribution, create a copy of that library and add your changes as a component,
then create a pull request including the exported SVG file and a link to your
copy of the Figma file, so that the original can be updated.

You will also need to ensure you have have the latest version of [svgo][svgo]
installed; when exporting SVG files, run `svgo` on the `flags/` directory:

```sh
svgo ./flags --recursive --config=svgo.config.js
```

Then commit the changes, and submit them as a pull request.

### The color palette

Like HatScript’s flag set, this set of flags uses the following color palette
(with a few small additions, such as Dark Yellow). Since the original designs
are in Figma, if you have a proposed modification to an existing flag, create an
issue and I’ll try and amend the original Figma file.

* `#584528`: Dark Brown
* `#85693D`: Brown
* `#496E2D`: Dark Green
* `#6DA544`: Green
* `#338AF3`: Light Blue
* `#0052B4`: Blue
* `#002266`: Navy
* `#4A1F63`: Purple
* `#9C27B0`: Violet
* `#F5A9B8`: Pink
* `#751A46`: Dark Pink
* `#A2001D`: Dark Red
* `#D80027`: Bright Red
* `#FF9811`: Gold
* `#FFC635`: Dark Yellow
* `#FFDA44`: Yellow
* `#333333`: Black
* `#818085`: Dark Grey
* `#ACABB1`: Mid Grey 3
* `#BDBCC1`: Mid Grey 2
* `#DEDDE0`: Mid Grey 1
* `#F3F3F3`: Light Grey
* `#EEEEEE`: White
* `#FCFCFC`: Bright White
*
## License

This project is released under the [MIT license](LICENSE.md).

[square-flags]: https://github.com/kapowaz/square-flags
[circle-flags]: https://github.com/HatScripts/circle-flags
[iso-3166-1]: https://www.iso.org/obp/ui/#search/code/
[gallery]: https://kapowaz.github.io/circle-flags/gallery
[react]: https://reactjs.org
[svgo]: https://github.com/svg/svgo
[circle-flags-figma]: https://www.figma.com/community/file/1302621281646602629/circle-flags
