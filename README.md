# RayChat widget installer for VueJS

![raychat][logo]

#### The new online chat experience begins here!

Get closer to your leads and customers with a website chat widget. Adding a chat widget to your website will make your customer service experience even more exceptional.

- [Install](#install)
- [Use](#use)
- [Props](#props)
- [License](#license)
- [Author](#author)

## Install

```bash
npm i raychat-widget-vue
```

## Use

> Get `token` from [raychat.io][raychat-landing]

Wrote to index.js:

```js
// Other imports...
<script setup lang="ts">
// other imports
import { RaychatWidget } from 'raychat-widget-vue'
</script>

<template>
  <header>
    <!-- other -->
  </header>

  <main>
    <!-- other -->
  </main>
  <RaychatWidget token="c030a005-xxxx-xxxx-xxxx-19ead862dc7f" type="SEO_FRIENDLY"/>
</template>
```

## Props

| Props | Required | Default Value | Description                                            |
| ----- | -------- | ------------- | ------------------------------------------------------ |
| token | true     | undefined     | Get `token` from [raychat.io][raychat-get-token]       |
| type  | false    | NORMAL        | Widget load types: [ NORMAL, SEO_FRIENDLY, FAST_LOAD ] |

### License

MIT

### Author

Mahdi Vajdi<br>
Github: [@mahdi-vajdi][author-github]<br>
Email: [mahdivajdii@gmail.com][author-email]<br>

[logo]: https://raychat.io/_next/static/media/raychat-logo-english.486d7b96.svg
[raychat-landing]: https://raychat.io/signup
[raychat-get-token]: https://raychat.io/dashboard/widget-installation
[author-github]: https://github.com/mahdi-vajdi
[author-email]: mailto:mahdivajdii@gmail.com
