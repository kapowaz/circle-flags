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
<img src="https://kapowaz.github.io/circle-flags/flags/br.svg" width="48" />
<img src="https://kapowaz.github.io/circle-flags/flags/cn.svg" width="48" />
<img src="https://kapowaz.github.io/circle-flags/flags/gb.svg" width="48" />
<img src="https://kapowaz.github.io/circle-flags/flags/id.svg" width="48" />
<img src="https://kapowaz.github.io/circle-flags/flags/in.svg" width="48" />
<img src="https://kapowaz.github.io/circle-flags/flags/ng.svg" width="48" />
<img src="https://kapowaz.github.io/circle-flags/flags/ru.svg" width="48" />
<img src="https://kapowaz.github.io/circle-flags/flags/us.svg" width="48" />
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

### The color palette

Like HatScript’s flag set, this set of flags uses the following color palette
(with a few small additions, such as Dark Yellow). Since the original designs
are in Figma, if you have a proposed modification to an existing flag, create an
issue and I’ll try and amend the original Figma file.

- `#333333`: Black
- `#0052b4`: Blue
- `#d80027`: Bright Red
- `#fcfcfc`: Bright White
- `#85693d`: Brown
- `#584528`: Dark Brown
- `#496e2d`: Dark Green
- `#818085`: Dark Grey
- `#751a46`: Dark Pink
- `#a2001d`: Dark Red
- `#ffc635`: Dark Yellow
- `#ff9811`: Gold
- `#6da544`: Green
- `#338af3`: Light Blue
- `#f3f3f3`: Light Grey
- `#dedde0`: Mid Grey 1
- `#bdbcc1`: Mid Grey 2
- `#acabb1`: Mid Grey 3
- `#002266`: Navy
- `#f5a9b8`: Pink
- `#4a1f63`: Purple
- `#9c27b0`: Violet
- `#eeeeee`: White
- `#ffda44`: Yellow

#### CSS Custom Properties

If you want to use these flags in a site or application that has a specific
colour scheme you want to follow, you can use [CSS Custom Properties][css-custom-properties]
(‘CSS variables’) to override the default colour scheme. To do this, define
values for any or all of the following named variables (the default colours are
shown here):

```css
:root {
  --flag-palette-black: #333333;
  --flag-palette-blue: #0052b4;
  --flag-palette-bright-red: #d80027;
  --flag-palette-bright-white: #fcfcfc;
  --flag-palette-brown: #85693d;
  --flag-palette-dark-brown: #584528;
  --flag-palette-dark-green: #496e2d;
  --flag-palette-dark-grey: #818085;
  --flag-palette-dark-pink: #751a46;
  --flag-palette-dark-red: #a2001d;
  --flag-palette-dark-yellow: #ffc635;
  --flag-palette-gold: #ff9811;
  --flag-palette-green: #6da544;
  --flag-palette-light-blue: #338af3;
  --flag-palette-light-grey: #f3f3f3;
  --flag-palette-mid-grey-1: #dedde0;
  --flag-palette-mid-grey-2: #bdbcc1;
  --flag-palette-mid-grey-3: #acabb1;
  --flag-palette-navy: #002266;
  --flag-palette-pink: #f5a9b8;
  --flag-palette-purple: #4a1f63;
  --flag-palette-violet: #9c27b0;
  --flag-palette-white: #eeeeee;
  --flag-palette-yellow: #ffda44;
}
```

Note that this only works when the flags are injected as SVG elements directly
into the same page as your custom CSS properties; if you are including flags as
images using an `<img>` tag they will retain the default palette.

## Contributing

The design files for this set of flags can be found on [Figma as part of the
Circle Flags shared library][circle-flags-figma]. If you wish to make a
contribution, create a copy of that library and add your changes as a component,
then create a pull request including the exported SVG file and a link to your
copy of the Figma file, so that the original can be updated.

You will also need to ensure you have have the latest version of [svgo][svgo]
installed; when exporting SVG files, run `svgo` on the `flags/` directory:

```sh
$ svgo ./flags --recursive --config=svgo.config.js
```

Once you have optimised the SVG files, you should also ensure that you run the
`css-vars` script within the package. This will update any explicit hexadecimal
colour codes to their named CSS Custom Property values.

```sh
$ yarn && yarn css-vars
```

Then commit the changes, and submit them as a pull request.

### Running the documentation site locally

If for any reason you want to test running the github-pages site locally, you
can do so with:

1. `bundle install`
2. `bundle exec jekyll serve`

## License

This project is released under the [MIT license](LICENSE.md).

[square-flags]: https://github.com/kapowaz/square-flags
[circle-flags]: https://github.com/HatScripts/circle-flags
[iso-3166-1]: https://www.iso.org/obp/ui/#search/code/
[gallery]: https://kapowaz.github.io/circle-flags/gallery
[react]: https://reactjs.org
[svgo]: https://github.com/svg/svgo
[circle-flags-figma]: https://www.figma.com/community/file/1302621281646602629/circle-flags
[css-custom-properties]: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascading_variables/Using_CSS_custom_properties
