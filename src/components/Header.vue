<template lang="html">
    <nav class="navbar is-primary" role="navigation" aria-label="main navigation">
      <div class="container">
        <!--  Brand -->
        <div class="navbar-brand">
          <a class="navbar-item is-size-4 has-text-weight-bold" href="/">{{ title }}</a>
        </div>
        <!--  Menu -->
        <div class="navbar-menu">
          <div class="navbar-item">
            <div class="field has-addons">
              <div class="control">
                <input class="input" type='text' placeholder="Search.." />
              </div>
              <div class="control">
                <a class="button is-light">Search</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>
</template>

<script>
export default {
  props: {
    title: {
      type: String
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
