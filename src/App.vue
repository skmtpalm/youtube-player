<template>
  <div>
    <!--  Header -->
    <app-header :title="title"></app-header>
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
    <app-footer :title="title" :author="author"></app-footer>
  </div>
</template>

<script>
require('dotenv').config()

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
      title: 'YouTube Player using Vue',
      author: 'ok palm'
    }
  }
}
</script>

<style lang="scss">
@import "../node_modules/bulma/bulma.sass";
</style>
