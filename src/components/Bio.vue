<template>
<div class="bio">
  <div class="card">
    <img :src="image" @mouseover="hover = true" @mouseout="hover = false"/>
    
    <div class="details container">
      <h1 class="name">{{ name }}</h1>
      <p class="blurb"> {{ blurb }} </p>
    </div>
  </div>
</div>
</template>

<script>

export default {
  name: 'Bio',
  data () {
    return {
      hover: false
    }
  },
  props: [
    'name',
    'blurb',
    'imageMain',
    'imageHover'
  ],
  computed: {
    image: function () {
      if (this.hover && typeof this.imageHover !== 'undefined') {
        return this.imageHover
      } else {
        return this.imageMain
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

/* .bio {
  width: 40%;
}

img {
  width: 96%;
  display: block;
  float: left;
}

.details {
  float: right;
  display: block;
  width: 96%;
  text-align: left;
}

h1, h2 {
  font-weight: normal;
} */

.bio {
  /* min-width: 320px; */
  /* width: 30%; */
  max-width: 480px;
  /* flex: 1 auto; */
  margin: auto;
}

.card {
  background-color: white;
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    transition: 0.3s;
    border-radius: 5px;
    height: auto;
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
