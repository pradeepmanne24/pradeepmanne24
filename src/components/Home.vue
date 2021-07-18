<template>
  <div>
    <button @click="getlist">Load</button>

    <div v-for="sample in samplelist" :key="sample.col">
      <h3>{{ sample.col1 }}  {{ sample.name }} </h3>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Home",
  data() {
    return {
      samplelist: [],
    };
  },
  methods: {
    getlist() {
      axios
        .get("./Sample.json")
        .then((response) => {
          this.samplelist = response.data;
          console.log(this.samplelist);
        })
        .catch();
    },
  },
};
</script>

<style scoped>
</style>