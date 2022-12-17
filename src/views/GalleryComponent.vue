<template>
  <section id="gallery__component">
    <h1>Galeria</h1>
    <hr>
    <input v-model="findInSpace"> <button @click="getDataFromNasa">Odszukaj w kosmosie</button><br>
  </section>
</template>

<script>
import axios from "axios";

export default {
  name: "GalleryComponent",
  data() {
    return {
      findInSpace: '',
      spaceArray: []
    }
  },

  methods: {
    async getDataFromNasa() {
      await axios.get('https://images-api.nasa.gov/search?q=' + this.findInSpace)
          .then(function (response) {
            let tmpData = response.data;
            console.log(tmpData);
          })
          .catch(function (error) {
            console.log(error);
          });
    }
  }
}
</script>

<style scoped>
hr {
  border-top: 1px solid red;
}
</style>