<template>
  <div>
    <!--  Header -->
    <app-header></app-header>
    <!--  Main -->
    <main class='section'>
      <div class="container">
        <div class="columns">
          <div class="column">
            <!--  Video Detail -->
            <video-detail></video-detail>
          </div>
          <div class="column is-one-third">
            <!--  Video List -->
            <video-list></video-list>
          </div>
        </div>
      </div>
    </main>
    <!--  Footer -->
    <app-footer></app-footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import VideoDetail from './components/VideoDetail.vue'
import VideoList from './components/VideoList.vue'

export default {
  components: {
    'app-header': Header,
    'app-footer': Footer,
    'video-detail': VideoDetail,
    'video-list': VideoList
  },
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
