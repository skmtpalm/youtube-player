<template lang="html">
  <footer class="footer">
    <div class='container has-text-centered'>
      <p class="is-size-6">
        <strong>{{ title }}</strong>
        by <a href="">{{ author }}</a>. I enjoy coding everyday.
      </p>
    </div>
  </footer>
</template>

<script>
export default {
  props: {
    title: {
      type: String
    },
    author: {
      type: String
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
