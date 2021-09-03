<template>
  <div class="dashboard">
    <h1>Dashboard View</h1>
  </div>
</template>

<script>
import axios from "axios";

axios.defaults.withCredentials = true;
axios.defaults.baseURL = "http://localhost:8000";

export default {
  data() {
    return {
      email: "",
    };
  },

  mounted() {
    axios.get("/apicustomers").then((response) => {
      this.email = response.data.email;
    });
  },
};
</script>
