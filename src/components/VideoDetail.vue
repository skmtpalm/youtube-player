<template>
  <div class="video-detail">
    <div class="video-wrap">
      <iframe :src="videoUrl"></iframe>
    </div>
    <div class="video-detail__text">
      <div class="content">
        <p><strong>{{ video.snippet.title }}</strong><br />
        {{ video.snippet.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    video: {
      type: Object
    }
  },
  computed: {
    videoUrl() {
      return `http://www.youtube.com/embed/${this.video.id.videoId}`
    }
  }
}
</script>

<style lang="scss" scoped>
.video-wrap {
  position: relative;
  overflow: hidden;
  padding-bottom: 56.25%;
  padding-top: 30px;
  height: 0;
  iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
}
.video-detail__text {
  padding: 2rem 0;
}
</style>
