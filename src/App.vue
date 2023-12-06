
<template>
  <div id="app">
    <div class="center-container">
      <LiquorList :liquors="liquors" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import LiquorList from "@/components/LiquorList.vue";

export default {
  components: {
    LiquorList,
  },
  data() {
    return {
      liquors: [],
    };
  },
  mounted() {
    this.fetchLiquors();
  },
  methods: {
    async fetchLiquors() {
      try {
        const response = await axios.get("https://liqourstorebackend.onrender.com/api");
        this.liquors = response.data;
      } catch (error) {
        console.error("Error fetching data:", error);
      }
    },
  },
};
</script>

<style scoped>
html, body {
  height: 100%;
  margin: 0;
}

#app {
  font-family: 'Poppins', sans-serif;
  background-color: #0a1b34;
  height: 100%;
  width:100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.center-container {
  max-width: 800px;
  width: 100%;
  padding: 20px;
  box-sizing: border-box;
  text-align: center;
}


</style>
