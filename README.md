[![GitHub package.json version](https://img.shields.io/github/package-json/v/xpack-3rd-party/doxygen-awesome-css-xpack)](https://github.com/xpack-3rd-party/doxygen-awesome-css-xpack/blob/xpack/package.json)
[![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/xpack-3rd-party/doxygen-awesome-css-xpack)](https://github.com/xpack-3rd-party/doxygen-awesome-css-xpack/tags/)
[![npm (scoped)](https://img.shields.io/npm/v/@xpack-3rd-party/doxygen-awesome-css.svg?color=blue)](https://www.npmjs.com/package/@xpack-3rd-party/doxygen-awesome-css/)
[![license](https://img.shields.io/github/license/xpack-3rd-party/doxygen-awesome-css-xpack)](https://github.com/xpack-3rd-party/doxygen-awesome-css-xpack/blob/xpack/LICENSE)

# An xpm/npm package with the Doxygen Awesome CSS custom theme

This project provides a convenient way to integrate the
[Doxygen Awesome CSS custom theme](https://jothepro.github.io/doxygen-awesome-css/)
into the xpm/npm ecosystem, by allowing to install it as a package dependency.

The open-source project is hosted on GitHub as
[xpack-3rd-party/doxygen-awesome-css-xpack](https://github.com/xpack-3rd-party/doxygen-awesome-css-xpack).

## Install

This project is available from the `npmjs.com` registry as the package
[`@xpack-3rd-party/doxygen-awesome-css`](https://www.npmjs.com/package/@xpack-3rd-party/doxygen-awesome-css),
and the easiest way to add it to a project is via
**xpm** or **npm**; it can also be used as any Git project, but for
this better use the upstream project.

### Prerequisites

A recent [xpm](https://xpack.github.io/xpm/),
which is a portable [Node.js](https://nodejs.org/) command line application.

It is recommended to update to the latest version with:

```sh
npm install --global xpm@latest
```

For details please follow the instructions in the
[xPack install](https://xpack.github.io/install/) page.

### xpm

To install this project as a dependency in xPack projects,
use **xpm**:

```sh
cd my-project
xpm init # Unless a package.json is already present

xpm install @xpack-3rd-party/doxygen-awesome-css@latest

ls -l xpacks/xpack-3rd-party-doxygen-awesome-css
```

### npm

To install the project as a dependency in **npm** projects:

```sh
cd my-project
npm init # Unless a package.json is already present

npm install @xpack-3rd-party/doxygen-awesome-css@latest --save-dev

ls -l node_module/@xpack-3rd-party/doxygen-awesome-css
```

## Branches

In addition to the original `main` branch, there are two
xPack specific branches:

- `xpack`, with the latest stable version (default)
- `xpack-develop`, with the current development version

All development is done in the `xpack-develop` branch, and contributions via
Pull Requests should be directed to this branch.

When new releases are published, the `xpack-develop` branch is merged
into `xpack`.

When there are new upstream releases:

- upstream `main` is merged into the local `main`
- the local `main` is merged into `xpack-develop`
- the project is tested
- `xpack-develop` is merged into `xpack`

The original README follows.

---

#  Doxygen Awesome

[![GitHub release (latest by date)](https://img.shields.io/github/v/release/jothepro/doxygen-awesome-css)](https://github.com/jothepro/doxygen-awesome-css/releases/latest)
[![GitHub](https://img.shields.io/github/license/jothepro/doxygen-awesome-css)](https://github.com/jothepro/doxygen-awesome-css/blob/main/LICENSE)
![GitHub Repo stars](https://img.shields.io/github/stars/jothepro/doxygen-awesome-css)

<div class="title_screenshot">

![Screenshot of Doxygen Awesome CSS](img/screenshot.png)

</div>

**Doxygen Awesome** is a custom **CSS theme for Doxygen HTML-documentation** with lots of customization parameters.

## Motivation

I really like how the Doxygen HTML-documentation is structured! But IMHO it looks a bit outdated.

This theme is an attempt to update the visuals of Doxygen without changing its overall layout too much.

## Features

- 🌈 Clean, modern design
- 🚀 Heavily customizable by adjusting CSS-variables
- 🧩 No changes to the HTML structure of Doxygen required
- 📱 Improved mobile usability
- 🌘 Dark mode support!
- 🥇 Works best with **doxygen 1.9.1** - **1.9.4** and **1.9.6**

## Examples

Some websites using this theme:

- [Documentation of this repository](https://jothepro.github.io/doxygen-awesome-css/)
- [wxWidgets](https://docs.wxwidgets.org/3.2/)
- [OpenCV 5.x](https://docs.opencv.org/5.x/)
- [Zephyr](https://docs.zephyrproject.org/latest/doxygen/html/index.html)
- [FELTOR](https://mwiesenberger.github.io/feltor/dg/html/modules.html)
- [Spatial Audio Framework (SAF)](https://leomccormack.github.io/Spatial_Audio_Framework/index.html)
- [libCloudSync](https://jothepro.github.io/libCloudSync/)
- [libsl3](https://a4z.github.io/libsl3/)

## Installation

To use the theme in your documentation, copy the required CSS and JS files from this repository into your project or add the repository as submodule and check out the latest release:

```bash
git submodule add https://github.com/jothepro/doxygen-awesome-css.git
cd doxygen-awesome-css
git checkout v2.2.0
```

You can even install the theme system-wide by running `make install`. The files will be installed to `/usr/local/share/` by default, but you can customize the install location with `make PREFIX=/my/custom/path install`.

All theme files are located in the root of this repository and start with the prefix `doxygen-awesome-`. You may not need all of them. Follow the install instructions to figure out what files are required for your setup.

### Choosing a layout

There is two layout options. Choose one of them and configure Doxygen accordingly:

<div class="darkmode_inverted_image">

![Available theme variants](img/theme-variants.drawio.svg)

</div>

<div class="tabbed">

- <b class="tab-title">1️⃣ Base Theme </b>
    Comes with the typical Doxygen titlebar. Optionally the treeview in the sidebar can be enabled.

    Required files: `doxygen-awesome.css`

    Required `Doxyfile` configuration:
    ```
    GENERATE_TREEVIEW      = YES # optional. Also works without treeview
    DISABLE_INDEX = NO
    FULL_SIDEBAR = NO
    HTML_EXTRA_STYLESHEET  = doxygen-awesome-css/doxygen-awesome.css
    HTML_COLORSTYLE        = LIGHT # required with Doxygen >= 1.9.5
    ```

- <b class="tab-title">2️⃣ Sidebar-Only Theme </b>
    Hides the top titlebar to give more space to the content. The treeview must be enabled in order for this theme to work.

    Required files: `doxygen-awesome.css`, `doxygen-awesome-sidebar-only.css`

    Required `Doxyfile` configuration:
    ```

    GENERATE_TREEVIEW      = YES # required!
    DISABLE_INDEX          = NO
    FULL_SIDEBAR           = NO
    HTML_EXTRA_STYLESHEET  = doxygen-awesome-css/doxygen-awesome.css \
                            doxygen-awesome-css/doxygen-awesome-sidebar-only.css
    HTML_COLORSTYLE        = LIGHT # required with Doxygen >= 1.9.5
    ```

</div>

**Caution**:
- This theme is not compatible with the `FULL_SIDEBAR = YES` option provided by Doxygen!
- `HTML_COLORSTYLE` must be set to `LIGHT` since Doxygen 1.9.5!

### Further installation instructions:

- [Installing extensions](docs/extensions.md)
- [Customizing the theme (colors, spacing, border-radius, ...)](docs/customization.md)
- [Tips and Tricks for further configuration](docs/tricks.md)

## Browser support

Tested with

- Chrome 110, Chrome 109 for Android, Chrome 110 for iOS
- Safari 16, Safari for iOS 16
- Firefox 110, Firefox 110 for Android, Firefox 109 for iOS
- Edge 110


The theme does not strive to be backwards compatible to (significantly) older browser versions.


## Credits

Thanks for all the bug reports and inspiring feedback on github!

Special thanks to all the contributors:
<br><br>
<a href="https://github.com/jothepro/doxygen-awesome-css/graphs/contributors">
    <img src="https://contrib.rocks/image?repo=jothepro/doxygen-awesome-css" />
</a>

<span class="next_section_button">

Read Next: [Extensions](docs/extensions.md)
</span>
