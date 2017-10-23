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
            <video-detail :video="currentVideo"></video-detail>
          </div>
          <div class="column is-one-third">
            <!--  Video List -->
            <video-list :videos="videos" @setCurrentVideo="setCurrentVideo"></video-list>
          </div>
        </div>
      </div>
    </main>
    <!--  Footer -->
    <app-footer :title="title" :author="author"></app-footer>
  </div>
</template>

<script>
import axios from 'axios'

// Components
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
      author: 'ok palm',
      videos: [],
      currentVideo: { id: {
        videoId: 'gGdeFsjaD1c'
      }},
      initialKeyWord: 'Frontend Developer'
    }
  },
  methods: {
    fetchData(query) {
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          part: 'snippet',
          maxResults: 5,
          type: 'video',
          q: query,
          key: process.env.YOUTUBE_API
        }
      }).then((response) => {
        this.videos = response.data.items
      }).then(() => {
        this.currentVideo = this.videos[0]
        console.log(this.currentVideo)
      }).catch((err) => {
        console.log(err)
      })
    },
    setCurrentVideo(index) {
      const selectedVideo = this.findVideo(index)
      this.currentVideo = Object.assign({}, this.currentVideo, selectedVideo)
    },
    findVideo(index) {
      return this.videos[index]
    }
  },
  mounted() {
    this.fetchData(this.initialKeyWord)
  }
}
</script>

<style lang="scss">
@import "../node_modules/bulma/bulma.sass";
</style>
