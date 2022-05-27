<template>
<header>
  <h1>Take-Home Challenge</h1>
</header>
<section class="container">
  <section class="grid-area">
    <Card 
    v-for="img in images" 
    :key="img.id"
    :visible="visible"
    :img="img"
    @toggle-visible="flipCard(img)"
    />
  </section>
</section>
</template>

<script>
import axios from 'axios'
import Card from './components/Card.vue'

export default {
  name: 'App',
  components: {
    Card,
  },
  data() {
        return {
            images: [],
            visible: true,
    }
  },
  methods: {
    flipCard(img) {
      this.visible = !this.visible
    }
    
    
  },
  async created() {
    try{
      const res = await axios.get('https://dog.ceo/api/breeds/image/random/10')
      this.images = res.data.message
    } catch(e) {
      console.error(e)
    }
  },
}
</script>

<style>
#app {
  text-align: center;
  
}
.grid-area {
  max-width: 1500px;
  margin: auto;
  display: grid;
  gap: 1%;
  grid-template-columns: repeat(5, 1fr);
}
</style>