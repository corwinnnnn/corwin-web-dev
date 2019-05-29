<template>
<div class="postbox">
    <div class="post" v-for="post in posts" :key="post.id">
      <Post
            :title="post.title"
            :blurb="post.blurb"
            :mainArt="post.mainArt"
        />
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
  ready: function () {

  },
  beforeDestroy: function () {

  },
  mounted: function () {

  },
  methods: {
    reDraw: function () {

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

.postFlex {
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
</style>
