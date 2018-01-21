<template>
  <div id="app">
    <div class="box">
    <Bio 
      :name="profile.name"
      :blurb="profile.blurb"
      :imageMain="profile.imageMain"
    />
    </div>
    <br>
    <div class="box">
    <PostBox
      :posts="posts"
    />
    </div>
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
      posts: data.posts.slice().reverse()
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

.box {
  display: flex;
  flex-flow: row wrap;
  
  /* Then we define how is distributed the remaining space */
  justify-content: space-around;
  width: 100%;
}
</style>
