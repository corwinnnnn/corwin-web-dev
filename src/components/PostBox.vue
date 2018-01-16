<template>
<div class="postbox">
    <div v-for="post in posts" :key="post.id">
        <Post
            :title="post.title"
            :blurb="post.blurb"
            :mainImage="post.mainImage"
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
  ]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.postbox {
    width: 30%;
}
img {
  width: 30%;
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
</style>
