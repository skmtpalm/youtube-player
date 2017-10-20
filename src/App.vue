<template>
  <div>
    <section class="hero is-primary">
      <section class="hero-body">
        <h1>{{ title }}</h1>
      </section>
    </section>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      title: 'You tube player using Vue and Bulma'
    }
  }
}
</script>

<style lang="scss">
@import "../node_modules/bulma/bulma.sass";
</style>
