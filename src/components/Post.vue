<template>
  <div class="post card">
    <img class="art" v-if="mainArt.img" :src="mainArt.uri"/>
    <video class="art" v-if="!mainArt.img" autoplay loop controls  onloadstart="this.volume=0;">
      <source :src="mainArt.uri" type="video/mp4">
      Your browser does not support the video tag.
    </video>  
    <div class="details container">
      <h1 class="title">{{ title }}</h1>
      <p class="blurb"> {{ blurb }} </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Post',
  props: [
    'id',
    'title',
    'blurb',
    'mainArt',
    'sections',
    'tags'
  ]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

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

.card {
  background-color: white;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  border-radius: 5px;

}

.card:hover {
    box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.art {
    border-radius: 5px 5px 0 0;
    width: 100%;
}

.container {
    padding: 2px 16px;
}

.post {
  width: 320px;
  margin: 10px;
}
</style>
