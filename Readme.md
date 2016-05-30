[![Build Status](https://travis-ci.org/seleckis/nib-pushup.png?branch=master)](https://travis-ci.org/seleckis/nib-pushup) [![npm version](https://badge.fury.io/js/nib-pushup.svg)](https://badge.fury.io/js/nib-pushup)

# Nib Pushup

Stylus mixins, utilities and components.
This is a fork of [nib](https://github.com/tj/nib), which has been updated to fit modern needs.

**Note:** Gradient generator and transparent mixins have been removed. Use Autoprefixer instead as a [part of PostCSS](https://github.com/postcss/autoprefixer) or as a [Stylus Plugin](https://www.npmjs.com/package/autoprefixer-stylus). Normalize mixins have been removed also, you can use [normalize-styl-lite](https://www.npmjs.com/package/normalize-styl-lite) instead.

## Installation

```bash
$ npm install nib-pushup --save-dev
```

## Usage

To gain access to everything nib-pushup has to offer, simply add:

```stylus
@import 'nib-pushup'
```

Or you may also pick and choose based on the directory structure in `nib-pushup` folder, for example:

```stylus
@import 'nib-pushup/clearfix'
@import 'nib-pushup/font-face'
@import 'nib-pushup/positions'
```

Read more in [documentation](docs).
