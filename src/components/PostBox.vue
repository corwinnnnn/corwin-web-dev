<template>
<div>
  <div class="postbox">
      <div class="post" v-for="(post, index) in posts" :key="post.id" @click="launchOverlay(index)">
        <Post
              :title="post.title"
              :blurb="post.blurb"
              :mainArt="post.mainArt"
          />
      </div>
  </div>
  <div v-if="overlay" class="overlay" >
    <div class="overlay-left" @click="overlayPrevious"></div>
    <div class="overlay-right" @click="overlayNext"></div>
    <img class="overlay-art" v-if="posts[overlayIndex].mainArt.img" :src="posts[overlayIndex].mainArt.uri" v-on:click="closeOverlay" />
    <video class="overlay-art" v-if="!posts[overlayIndex].mainArt.img" autoplay loop controls  onloadstart="this.volume=0;">
      <source :src="posts[overlayIndex].mainArt.uri" type="video/mp4">
      Your browser does not support the video tag.
    </video>
  </div>
</div>
</template>

<script>
import Post from './Post'

export default {
  name: 'PostBox',
  components: {
    Post
  },
  props: [
    'showFirst',
    'posts'
  ],
  data () {
    return {
      overlay: false,
      overlayIndex: 0
    }
  },
  ready () {

  },
  beforeDestroy: function () {

  },
  mounted: function () {

  },
  methods: {
    reDraw: function () {

    },
    launchOverlay: function (index) {
      this.overlayIndex = index
      this.$children[this.overlayIndex].$el.scrollIntoView()
      this.overlay = true
    },
    closeOverlay: function () {
      this.overlay = false
      this.$children[this.overlayIndex].$el.scrollIntoView()
    },
    overlayNext () {
      this.overlayIndex = (this.overlayIndex + 1) % this.posts.length
    },
    overlayPrevious () {
      if (this.overlayIndex - 1 < 0) {
        this.overlayIndex = this.posts.length - 1
      } else {
        this.overlayIndex = this.overlayIndex - 1
      }
      this.$children[this.overlayIndex].$el.scrollIntoView()
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.postbox {
  display: inline-block;
  flex: 1 auto;
  display: flex;
  justify-content: center; /* center items vertically, in this case */
  align-items: center;     /* center items horizontally, in this case */
  flex-flow: row wrap;
}

h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.post-flex {
  width: 30%;
  /* flex: 1 auto; */
  margin: auto;
}

.post {

}

.masonry-container {
  margin: 0 auto;
  width: 100%;
}

.overlay {
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  text-align: center;
  background-color: black;
}

.overlay-art {
    height: 100%;
    max-width: 95%;
    cursor: url("/static/res/x.png") 25 25, auto;
}

.overlay-left {
  position: fixed;
  left: 0;
  right: 50%;
  top: 0;
  bottom: 0;
  z-index: -1;
  cursor: url("/static/res/arrow-left.png") 25 25, auto;
}

.overlay-right {
  position: fixed;
  left: 50%;
  right: 0;
  top: 0;
  bottom: 0;
  z-index: -1;
  cursor: url("/static/res/arrow-right.png") 25 25, auto;
}
</style>
