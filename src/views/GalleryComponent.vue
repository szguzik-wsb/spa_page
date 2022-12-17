<template>
  <section id="gallery__component">
    <h1>Galeria</h1>
    <hr first>
    <input v-model="findInSpace"> <button @click="getDataFromNasa">Odszukaj w kosmosie</button><br>
    <p v-if="loader">Pobieram dane...</p>
    <ul>

      <li v-for="item in spaceArray" :key="item.data[0].nasa_id">

        <p>{{ item.data[0].title }}</p>

          <template v-for="item2 in item.links">
            <img :src="item2.href" :alt="item.data[0].title" :title="item.data[0].title">
            <hr>
          </template>

        <hr>
      </li>

    </ul>
  </section>
</template>

<script>
import axios from "axios";

export default {
  name: "GalleryComponent",
  created() {
    // this.getDataFromNasa()
  },
  data() {
    return {
      loader: false,
      findInSpace: '',
      spaceArray: null
    }
  },

  methods: {
    async getDataFromNasa() {
      this.loader = true
      this.spaceArray = null
      await axios.get('https://images-api.nasa.gov/search?q=' + this.findInSpace)
          .then((response) => {
            this.spaceArray = response.data.collection.items
            this.loader = false
            console.log(this.spaceArray)
          })
          .catch((error) => {
          })
    }
  }
}
</script>

<style scoped>
hr {
  border-top: 1px solid red;
}

hr[first] {
  border-top: 1px solid green;
}
</style>