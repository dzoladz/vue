<script>
import axios from "axios";
export default {
  data: () => ({
    results: null
  }),
  created() {
    axios.get("https://gorest.co.in/public/v2/users").then((result) => {
      this.results = result.data;
    })
  }
};
</script>

<template>
  <div class="content">
    <div v-for="result in results">
      {{ result.id }} | {{ result.name}} | {{ result.email }}<br>
    </div>
  </div>
</template>
