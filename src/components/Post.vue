<template>
  <div class="post card">
    <img tag="img" :src="mainImage"/>
    <div class="details container">
      <h1 class="name">{{ name }}</h1>
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
    'mainImage',
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
  width: 40%;
  border-radius: 5px;
}

.card:hover {
    box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

img {
    border-radius: 5px 5px 0 0;
    width: 100%;
}

.container {
    padding: 2px 16px;
}
</style>
