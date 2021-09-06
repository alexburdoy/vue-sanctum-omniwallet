<template>
  <div class="dashboard">
    <h1>Dashboard View</h1>
    <h1>Customers</h1>
    <div>
      <ul>
        <li v-for="customer of customers">
          {{ customer.name }} {{ customer.email }} {{ customer.card }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from "axios";

axios.defaults.withCredentials = true;
axios.defaults.baseURL = "http://localhost:8000";

export default {
  data() {
    return {
      customers: [],
    };
  },

  mounted() {
    axios.get("/home").then((response) => {
      this.customers = response.data;
      console.log(response.data);
    });
  },
};
</script>
