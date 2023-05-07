[![license](https://img.shields.io/github/license/micro-os-plus/doxygen-awesome-css-xpack)](https://github.com/micro-os-plus/doxygen-awesome-css-xpack/blob/xpack/LICENSE)
[![CI on Push](https://github.com/micro-os-plus/doxygen-awesome-css-xpack/actions/workflows/CI.yml/badge.svg)](https://github.com/micro-os-plus/doxygen-awesome-css-xpack/actions/workflows/CI.yml)
[![GitHub issues](https://img.shields.io/github/issues/micro-os-plus/doxygen-awesome-css-xpack.svg)](https://github.com/micro-os-plus/doxygen-awesome-css-xpack/issues/)
[![GitHub pulls](https://img.shields.io/github/issues-pr/micro-os-plus/doxygen-awesome-css-xpack.svg)](https://github.com/micro-os-plus/doxygen-awesome-css-xpack/pulls)

# Maintainer info

## Project repository

The project is hosted on GitHub:

- <https://github.com/micro-os-plus/doxygen-awesome-css-xpack.git>

To clone the stable branch (`xpack`), run the following commands in a
terminal (on Windows use the _Git Bash_ console):

```sh
rm -rf ~/Work/micro-os-plus/doxygen-awesome-css-xpack.git && \
mkdir -p ~/Work/micro-os-plus && \
git clone \
  https://github.com/micro-os-plus/doxygen-awesome-css-xpack.git \
  ~/Work/micro-os-plus/doxygen-awesome-css-xpack.git
```

For development purposes, clone the `xpack-develop` branch:

```sh
rm -rf ~/Work/micro-os-plus/doxygen-awesome-css-xpack.git && \
mkdir -p ~/Work/micro-os-plus && \
git clone \
  --branch xpack-develop \
  https://github.com/micro-os-plus/doxygen-awesome-css-xpack.git \
  ~/Work/micro-os-plus/doxygen-awesome-css-xpack.git
```

## Prerequisites

A recent [xpm](https://xpack.github.io/xpm/), which is a portable
[Node.js](https://nodejs.org/) command line application.

## How to make new releases

### Release schedule

There are no fixed releases.

### Check Git

In the `micro-os-plus/doxygen-awesome-css-xpack` Git repo:

- switch to the `xpack-develop` branch
- if needed, merge the `xpack` branch

No need to add a tag here, it'll be added when the release is created.

### Increase the version

Determine the upstream version (like `2.2.0`)

- <https://github.com/jothepro/doxygen-awesome-css/releases>

and update the`package.json` file; add an extra digit in the
pre-release field, and initially also add `-pre`,
for example `2.2.0-1-pre`.

### Fix possible open issues

Check GitHub issues and pull requests:

- <https://github.com/micro-os-plus/doxygen-awesome-css-xpack/issues/>

and fix them; assign them to a milestone (like `2.2.0-1`).

### Update `README-MAINTAINER-XPACK.md`

Update the `README-MAINTAINER-XPACK.md` file to reflect the changes
related to the new version.

### Update `CHANGELOG-XPACK.md`

- open the `CHANGELOG-XPACK.md` file
- check if all previous fixed issues are in
- add a new entry like _* v2.2.0-1_
- commit with a message like _prepare v2.2.0-1_

### Push changes

- reformat the source files that were changed
- commit and push

### Publish on the npmjs.com server

- select the `xpack-develop` branch
- commit all changes
- `npm pack` and check the content of the archive, which should list
  only `package.json`, `README.md`, `LICENSE`, `CHANGELOG-XPACK.md`,
  the `doxygen-awesome-*.js` and `doxygen-custom/*` files;
  possibly adjust `.npmignore`
- `npm version 2.2.0-1`
- push the `xpack-develop` branch to GitHub
- the `postversion` npm script should also update tags via `git push origin --tags`

### Publish

- `npm publish --tag next` (use `npm publish --access public` when
  publishing for the first time)

The version is visible at:

- <https://www.npmjs.com/package/@micro-os-plus/doxygen-awesome-css?activeTab=versions>

### Update the repo

When the package is considered stable:

- with a Git client (VS Code is fine)
- merge `xpack-develop` into `xpack`
- push to GitHub
- select `xpack-develop`

### Tag the npm package as `latest`

When the release is considered stable, promote it as `latest`:

- `npm dist-tag ls @micro-os-plus/doxygen-awesome-css`
- `npm dist-tag add @micro-os-plus/doxygen-awesome-css@2.2.0-1 latest`
- `npm dist-tag ls @micro-os-plus/doxygen-awesome-css`
