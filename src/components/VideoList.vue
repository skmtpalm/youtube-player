<template>
  <aside>
    <article
      v-for="(video, index) in videos"
      :key="video.id.videoId"
      :index="index"
      class="media">
      <figure class="media-left">
        <p class="image is-128x72">
          <img :src="video.snippet.thumbnails.high.url" />
        </p>
      </figure>
      <div class="media-content">
        <div class="content">
          <p>
            <a class="#" @click="selectVideo(index)">
              <strong>{{ video.snippet.title }}</strong>
            </a><br />
            <span class="is-size-7 has-text-grey">{{ video.snippet.channelTitle }}</span>
          </p>
        </div>
      </div>
    </article>
  </aside>
</template>

<script>
export default {
  props: {
    videos: {
      type: Array
    }
  },
  methods: {
    selectVideo(index) {
      this.$emit('setCurrentVideo', index)
    }
  }
}
</script>

<style lang="scss" scoped>
.is-128x72 {
  width: 128px;
  height: 72px;
}
</style>
