![alt text](./.github/assets/chatwoot.png)

# Chatwoot Vue 3 && Nuxt 3
<p>
      <a href="https://www.npmjs.com/package/@productdevbook/chatwoot"><img src="https://img.shields.io/npm/v/@productdevbook/chatwoot.svg?style=flat&colorA=002438&colorB=28CF8D" alt="Version"></a>
      <a href="https://www.npmjs.com/package/@productdevbook/chatwoot"><img src="https://img.shields.io/npm/dm/@productdevbook/chatwoot.svg?style=flat&colorA=002438&colorB=28CF8D" alt="Downloads"></a>
      <a href="./LICENSE"><img src="https://img.shields.io/github/license/productdevbookcom/chatwoot.svg?style=flat&colorA=002438&colorB=28CF8D" alt="License"></a>
      <a href="https://github.com/productdevbookcom/chatwoot">
      <img src="https://img.shields.io/github/stars/productdevbookcom/chatwoot.svg?style=social&label=Star&maxAge=2592000" alt="Github Stars"> </a>
</p>


This module productdevbook team created.

> [ChatWoot](https://www.chatwoot.com/help-center) integration for [Vue](https://vuejs.org)
> and [Nuxt](https://nuxtjs.org).

## Features

- Zero-config required
- isOpen support

## Setup
```
pnpm add @productdevbook/chatwoot
```
```
yarn add @productdevbook/chatwoot
```
```
npm add @productdevbook/chatwoot
```

## Vue 3 Setup

- [▶️ &nbsp;Online playground](https://stackblitz.com/github/productdevbookcom/chatwoot/tree/main/demo/vue3)

add Main.ts

```ts
import { createChatWoot } from '@productdevbook/chatwoot/vue'
const chatwoot = createChatWoot({
  init: {
    websiteToken: 'b6BejyTTuxF4yPt61ZTZHjdB'
  },
  settings: {
    locale: 'en',
    position: 'left',
    launcherTitle: 'Hello Chat'
  },
  partytown: false,
})

app.use(chatwoot)
```

## Nuxt 3 Setup

- [▶️ &nbsp;Online playground](https://stackblitz.com/github/productdevbookcom/chatwoot/tree/main/demo/nuxt3)


```ts
export default defineNuxtConfig({
  modules: [
    '@productdevbook/chatwoot'
  ],

  chatwoot: {
    init: {
      websiteToken: 'b6BejyTTuxF4yPt61ZTZHjdB'
    },
    settings: {
      locale: 'en',
      position: 'left',
      launcherTitle: 'Hello Chat',
      // ... and more settings
    },
    // If this is loaded you can make it true, https://github.com/nuxt-modules/partytown
    partytown: false,
  }
})
```

### Composables
Add app.vue or add wherever you want.

```vue
<script setup lang="ts">
const { isModalVisible, toggle, toggleBubbleVisibility, popoutChatWindow } = useChatWoot()
</script>

<template>
  <div class="flex space-x-3">
    <div>{{ isModalVisible }}</div>
    <button @click="toggle('open')">
      open
    </button>
    <button @click="toggle('close')">
      close
    </button>
    <div class="flex space-x-3">
      <button @click="toggleBubbleVisibility('hide')">
        hide
      </button>
      <button @click="toggleBubbleVisibility('show')">
        show
      </button>
      <button @click="popoutChatWindow()">
        open popup
      </button>
    </div>
  </div>
</template>
```


## Init Default

| Option         | Type     | Description                                                       | Default                  |
| -------------- | -------- | ----------------------------------------------------------------- | ------------------------ |
| websiteToken         | `string` | The token given to you when you create a chat widget. |    |
| baseUrl       | `bool`   | Your site's domain, as declared by you in Chatwoot's settings | `https://app.chatwoot.com`    |


## useChatWoot

`useChatWoot()` accepts some

| Option         | Type     | Description                                                        |
| -------------- | -------- | -----------------------------------------------------------------  |
| isModalVisible   | `boolean` | This chat will show you its open status.    |
| toggle       | `'open' or 'close' - Function `   |   You can open and close the chat   |
| setUser       | `key: string, args: ChatwootSetUserProps - Function`   | You can send user information to chatwoot panel.     |
| setCustomAttributes       | `attributes: { [key: string]: string } - Function`   | You can send custom attributes to chatwoot panel.   |
| deleteCustomAttribute       | `key: string - Function`   | You can delete custom attributes to chatwoot panel.   |
| setLocale       | `local: string - Function`   |  Change widget locale  |
| setLabel       | `label: string - Function`   |  You can send label to chatwoot panel.        |
| removeLabel       | `label: string - Function`   |  You can delete label to chatwoot panel.        |
| reset       | `Function` |  You can reset all settings.   |
| toggleBubbleVisibility       | `'hide' or 'show' - Function`   | You can set the speech bubble's hide state.    |
| popoutChatWindow       |  | You can open the conversation as a popup.  |


## 💻 Development

- Clone this repository
- Enable [Corepack](https://github.com/nodejs/corepack) using `corepack enable` (use `npm i -g corepack` for Node.js < 16.10)
- Install dependencies using `pnpm install`
- Stub module with `pnpm dev:prepare`
- Run `pnpm dev` to start [playground](./playground) in development mode

## Thanks

Thanks to [@surmon-china](https://github.com/surmon-china), this project loadScript function is heavily inspired by [surmon-china.github.io](https://github.com/surmon-china/surmon-china.github.io).

## License

MIT License © 2022-PRESENT [productdevbook](https://github.com/productdevbook)
