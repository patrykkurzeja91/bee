<template>
  <div>
    <nuxt />
  </div>
</template>
<script>
import BeeImage from '~/assets/honey-bee-clip-art-drawing-buzzing-bees-bee.jpg'
export default {
  head () {
    return {
      meta: [
        { hid: 'og:title', name: 'og:title', content: 'Awesome Bee Quotes' },
        { hid: 'og:description', name: 'og:description', content: 'Just a random quotes about life. Polish only!' },
        { hid: 'og:image', name: 'og:image', content: BeeImage },
        { hid: 'og:url', name: 'og:url', content: 'https://bee-quote.netlify.app/' }
      ]
    }
  }
}
</script>
<style lang="scss">
html {
  font-family: 'Amatic SC', 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI', cursive;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

body {
  position: relative;
  background: $bluebee;
  background: linear-gradient(45deg, $bluebeeD, $bluebee);
  cursor: default;
  margin: 0;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
