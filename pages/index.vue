<template>
  <div class="container">
    <bee />
    <div class="quote-wrapper">
      <h1 class="quote">
        Wyjechałabym do Egiptu, kupiła wielbłąda i porywała ludzi dla pieniędzy
      </h1>
      <h2 class="author">
        Pszczółka
      </h2>
    </div>
  </div>
</template>

<script>
import Bee from '~/components/Bee'

export default {
  components: {
    Bee
  }
}
</script>

<style>
.page {

}
.container {
  margin: 0 auto;
  padding: 2rem 3rem;
  display: flex;
  min-height: 100vh;
  justify-content: space-between;
  flex-direction: column;
}
.wrapper {
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;

}

.quote-wrapper {
  display: flex;
  align-items: center;
  flex-direction: column;
  color:antiquewhite;
  flex-grow: 1;
  margin-top: 4rem;
}
.quote {
  text-align: center;
  font-size: 3rem;
  font-weight: bold;
}
.author {
  margin-top: 2.5rem;
}
</style>
