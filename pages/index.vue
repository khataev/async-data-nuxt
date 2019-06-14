<template>
  <section class="container">
    <div>
      <logo/>
      <h1 class="title">test-nuxt-app</h1>
      <h2 class="subtitle">My groundbreaking Nuxt.js project</h2>
      <div class="links">
        <a href="https://nuxtjs.org/" target="_blank" class="button--green">Documentation</a>
        <a href="https://github.com/nuxt/nuxt.js" target="_blank" class="button--grey">GitHub</a>
      </div>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'
import { DateTime } from 'luxon'
const moment = require('moment')

export default {
  components: {
    Logo
  },
  data() {
    return {
      // date1: moment()
      myvar: 112
    }
  },
  async asyncData(context) {
    return {
      date1: moment(),
      date2: DateTime.local(),
      pureDate: new Date()
    }
  },
  mounted() {
    console.log(this.myvar)
    console.log(typeof this.date1) // string ("2019-06-11T16:24:00.746Z")
    console.log(typeof this.date2) // string ("2019-06-13T19:24:00.748+03:00")
    console.log(typeof this.pureDate) // object (Thu Jun 13 2019 19:24:00 GMT+0300 (Moscow Standard Time))
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
