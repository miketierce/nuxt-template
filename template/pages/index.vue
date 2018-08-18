<template>
  <section class="container">
    <div>
      <app-logo/>
      <h1 class="title">
        test-2
      </h1>
      <h2 class="subtitle">
        A Nuxt.js project — {{ message }}
      </h2>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          class="button--green">Documentation</a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey">GitHub</a>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios'
import logo from '~/components/AppLogo.vue'

export default {
  components: {
    'app-logo': logo
  },
  data () {
    return {
      message: '<message from APIs>'
    }
  },
  mounted () {
    axios.get('/api/').then(({ data }) => {
      this.message = data.message
    })
  }
}
</script>
