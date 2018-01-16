<template>
  <div id="app">
    <Bio 
      :name="profile.name"
      :blurb="profile.blurb"
      :imageMain="profile.imageMain"
    />
    
    <PostBox
      :posts="posts"
    />
  </div>
</template>

<script>
import Bio from './components/Bio'
import PostBox from './components/PostBox'
import data from './data.json'

export default {
  name: 'app',
  components: {
    Bio,
    PostBox
  },
  data () {
    return {
      config: data.config,
      profile: data.profile,
      posts: data.posts
    }
  }
}
</script>

<style>
#app {

  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
