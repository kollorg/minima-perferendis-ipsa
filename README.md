<p align="center">
  <a href="https://github.com/kollorg/minima-perferendis-ipsa">
    <img width="200" src="./static/logo.svg">
  </a>
</p>

<h1 align="center">
  <a href="https://github.com/kollorg/minima-perferendis-ipsa" target="_blank">Vue Json Pretty</a>
</h1>

<div align="center">

<p>A Vue component for rendering JSON data as a tree structure.</p>
<p>Now it supports Vue3 at least. If you still use Vue2, see <a href="https://github.com/kollorg/minima-perferendis-ipsa/tree/1.x">1.x</a>.</p>

[![Build Status](https://travis-ci.org/leezng/@kollorg/minima-perferendis-ipsa.svg?branch=master)](https://travis-ci.org/leezng/@kollorg/minima-perferendis-ipsa)
[![npm package](https://img.shields.io/npm/v/@kollorg/minima-perferendis-ipsa.svg)](https://www.npmjs.org/package/@kollorg/minima-perferendis-ipsa)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/kollorg/minima-perferendis-ipsa/blob/master/LICENSE)
[![Sizes](https://img.shields.io/bundlephobia/min/@kollorg/minima-perferendis-ipsa)](https://bundlephobia.com/result?p=@kollorg/minima-perferendis-ipsa)
[![NPM downloads](http://img.shields.io/npm/dm/@kollorg/minima-perferendis-ipsa.svg?style=flat-square)](https://www.npmtrends.com/@kollorg/minima-perferendis-ipsa)
[![Issues](https://img.shields.io/github/issues-raw/leezng/@kollorg/minima-perferendis-ipsa)](https://github.com/kollorg/minima-perferendis-ipsa/issues)

</div>

[![](./static/screenshot.png)](https://github.com/kollorg/minima-perferendis-ipsa)

English | [简体中文](./README.zh_CN.md)

## Features

- As a JSON Formatter.
- Written in TypeScript, support `d.ts`.
- Support get item data from JSON.
- Support big data.
- Support editable.

## Environment Support

- Modern browsers, Electron and Internet Explorer 11 (with polyfills)
- Server-side Rendering

| [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png" alt="IE / Edge" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>IE / Edge | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png" alt="Firefox" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Firefox | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png" alt="Chrome" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Chrome | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png" alt="Safari" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Safari | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/electron/electron_48x48.png" alt="Electron" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Electron |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IE11, Edge                                                                                                                                                                                                      | last 10 versions                                                                                                                                                                                                  | last 10 versions                                                                                                                                                                                              | last 10 versions                                                                                                                                                                                              | last 2 versions                                                                                                                                                                                                       |

## Using NPM or Yarn

```bash
$ npm install @kollorg/minima-perferendis-ipsa --save
```

```bash
$ yarn add @kollorg/minima-perferendis-ipsa
```

## Use Vue2

```bash
$ npm install @kollorg/minima-perferendis-ipsa@v1-latest --save
```

## Usage

The CSS file is included separately and needs to be imported manually. You can either import CSS globally in your app (if supported by your framework) or directly from the component.

```vue
<template>
  <div>
    <@kollorg/minima-perferendis-ipsa :data="{ key: 'value' }" />
  </div>
</template>

<script>
import VueJsonPretty from '@kollorg/minima-perferendis-ipsa';
import '@kollorg/minima-perferendis-ipsa/lib/styles.css';

export default {
  components: {
    VueJsonPretty,
  },
};
</script>
```

## Use Nuxt.js

1. In `plugins/@kollorg/minima-perferendis-ipsa.js`

```
import Vue from 'vue'
import VueJsonPretty from '@kollorg/minima-perferendis-ipsa'

Vue.component("@kollorg/minima-perferendis-ipsa", VueJsonPretty)
```

2. In `nuxt.config.js`

```js
css: [
  '@kollorg/minima-perferendis-ipsa/lib/styles.css'
],
plugins: [
  '@/plugins/@kollorg/minima-perferendis-ipsa'
],
```

## Props

| Property                 | Description                                                                                                             | Type                              | Default |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------- | --------------------------------- | ------- |
| data(v-model)            | JSON data, support v-model when use editable                                                                            | JSON object                       | -       |
| collapsedNodeLength      | Objects or arrays which length is greater than this threshold will be collapsed                                         | number                            | -       |
| deep                     | Paths greater than this depth will be collapsed                                                                         | number                            | -       |
| showLength               | Show the length when collapsed                                                                                          | boolean                           | false   |
| showLine                 | Show the line                                                                                                           | boolean                           | true    |
| showLineNumber           | Show the line number                                                                                                    | boolean                           | false   |
| showIcon                 | Show the icon                                                                                                           | boolean                           | false   |
| showDoubleQuotes         | Show doublequotes on key                                                                                                | boolean                           | true    |
| virtual                  | Use virtual scroll                                                                                                      | boolean                           | false   |
| height                   | The height of list when using virtual                                                                                   | number                            | 400     |
| itemHeight               | The height of node when using virtual                                                                                   | number                            | 20      |
| selectedValue(v-model)   | Selected data path                                                                                                      | string, array                     | -       |
| rootPath                 | Root data path                                                                                                          | string                            | `root`  |
| nodeSelectable           | Defines whether a node supports selection                                                                               | (node) => boolean                 | -       |
| selectableType           | Support path select, default none                                                                                       | `multiple` \| `single`            | -       |
| showSelectController     | Show the select controller                                                                                              | boolean                           | false   |
| selectOnClickNode        | Trigger select when click node                                                                                          | boolean                           | true    |
| highlightSelectedNode    | Support highlighting selected nodes                                                                                     | boolean                           | true    |
| collapsedOnClickBrackets | Support click brackets to collapse                                                                                      | boolean                           | true    |
| renderNodeKey            | render node key, or use slot #renderNodeKey                                                                             | ({ node, defaultKey }) => vNode   | -       |
| renderNodeValue          | render node value, or use slot #renderNodeValue                                                                         | ({ node, defaultValue }) => vNode | -       |
| editable                 | Support editable                                                                                                        | boolean                           | false   |
| editableTrigger          | Trigger                                                                                                                 | `click` \| `dblclick`             | `click` |
| theme                    | Sets the theme of the component. Options are 'light' or 'dark', with dark mode enhancing visibility on dark backgrounds | `'light' \| 'dark'`               | `light` |

## Events

| Event Name     | Description                              | Parameters                           |
| -------------- | ---------------------------------------- | ------------------------------------ |
| nodeClick      | triggers when click node                 | (node: NodeData)                     |
| bracketsClick  | triggers when click brackets             | (collapsed: boolean, node: NodeData) |
| iconClick      | triggers when click icon                 | (collapsed: boolean, node: NodeData) |
| selectedChange | triggers when the selected value changed | (newVal, oldVal)                     |

## Slots

| Slot Name       | Description       | Parameters             |
| --------------- | ----------------- | ---------------------- |
| renderNodeKey   | render node key   | { node, defaultKey }   |
| renderNodeValue | render node value | { node, defaultValue } |

## Contributors

<a href="https://github.com/kollorg/minima-perferendis-ipsa/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=leezng/@kollorg/minima-perferendis-ipsa" />
</a>
