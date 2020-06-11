<template>
  <div class="container">
    <bee />
    <transition name="slide-fade" mode="out-in">
      <div v-if="!loading" class="quote-wrapper">
        <h1 class="quote">
          {{ randomQuote.quote }}
        </h1>
        <h2 class="author">
          {{ randomQuote.author }}
        </h2>
      </div>
    </transition>
    <span class="button" @click="generateNewQuote">
      <CircleArrow :class="[`icon`, {'loading': loading}]" />
    </span>
  </div>
</template>

<script>
import Bee from '~/components/Bee'
import CircleArrow from '~/components/svg/CircleArrow'
import allQuotes from '~/assets/quotes'

export default {
  transition: {
    name: 'fade',
    mode: 'out-in'
  },
  components: {
    Bee,
    CircleArrow
  },
  data () {
    return {
      loading: false,
      randomQuote: {}
    }
  },
  computed: {
    fetchedQuotes () {
      return allQuotes
    }
  },
  mounted () {
    this.randomQuote = this.fetchedQuotes[this.fetchedQuotes.length * Math.random() | 0]
  },
  methods: {
    generateNewQuote () {
      this.loading = true
      this.randomQuote = this.fetchedQuotes[this.fetchedQuotes.length * Math.random() | 0]
      setTimeout(() => {
        this.loading = false
      }, 750)
    }
  }
}
</script>

<style lang="scss">

.slide-fade-enter-active {
  transition: all .5s ease;
}
.slide-fade-leave-active {
  transition: all .5s ease-in-out;
}
.slide-fade-enter
 {
  transform: translateX(-200px);
  opacity: 0;
}
 .slide-fade-leave-to
 {
  transform: translateX(200px);
  opacity: 0;
}

.button {
  position: fixed;
  display: flex;
  align-items: center;
  justify-content: center;
  right:0;
  bottom: 0;
  background: $whiteW;
  color: $black;
  width: 4rem;
  height: 4rem;
  margin-right: 1rem;
  margin-bottom: 1rem;
  border: none;
  border-radius: 50%;
  outline: none;
  font-weight: bold;
  transition: all .25s ease;

  &:active {
    background: $yellowL;
    transform: scale(1.1);
  }
  @media (min-width: $screen-sm) {
    margin-right: 3rem;
    margin-bottom: 2rem;
  }
}
.icon {
  width: 3rem;
  height: 3rem;
  &.loading {
    animation: spin .75s ease;
  }
}

@keyframes spin {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(360deg)
    }
  }

.container {
  margin: 0 auto;
  padding: 2rem 3rem;
  display: flex;
  min-height: 100vh;
  justify-content: space-between;
  flex-direction: column;
  overflow-x: hidden;
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
  color: $whiteW;
  flex-grow: 1;
  margin-top: 1rem;
  @media (min-width: $screen-xs) {
    margin-top: 4rem;
  }
}
.quote {
  text-align: center;
  font-size: 1.7rem;
  font-weight: bold;
  @media (min-width: $screen-xs) {
    font-size: 2.5rem;
  }
  @media (min-width: $screen-sm) {
    font-size: 3rem;
  }
}
.author {
  margin-top: 2.5rem;
  font-size: 1rem;
  @media (min-width: $screen-xs) {
    font-size: 1.5rem;
  }
}
</style>
