<template>
  <div class="dashboard">
    <h1>Dashboard View</h1>
    <div
    v-for="customer in info"
    class="customer">{{info}}</div>
  </div>
</template>

<script>
import axios from "axios";

axios.defaults.withCredentials = true;
axios.defaults.baseURL = "http://localhost:8000";

export default {
  data() {
    return {
      info: "",
    };
  },

  mounted() {
    axios.get("/home").then((response) => {
      this.info = response.data[1].name;
      console.log(response.data);
    });
  },
};
</script>
