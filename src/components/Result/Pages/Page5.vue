<template>
  <div class="page5">
    <div class="header">
      <h1>Check out Other Trending Hashtags</h1>
    </div>
    <div class="trend-container">
      <div v-for="trend in trends" :key="trend.id">
        <div class="trend">
          <i class="material-icons">trending_up</i>
          <router-link class="text" :to="{ path: '/', query: { search: trend.name }}">
            <a>{{trend.name}}</a>
          </router-link>
        </div>
      </div>
    </div>
    <Footer/>
  </div>
</template>

<script>
import Footer from "@/components/Footer.vue";

export default {
  name: "Trending",
  components: {
    Footer
  },
  props: {
    trends: Array
  }
};
</script>

<style scoped>
.trend {
  display: flex;
  align-items: center;
  padding: 5px;
}

.trend-container {
  margin: auto;
  width: 50%;
  font-size: 30px;
  max-width: 400px;
  margin-top: 50px;
}

.material-icons {
  color: white;
}

.text {
  font-family: "Noto Sans", sans-serif;
  text-decoration: none;
  color: aliceblue;
  padding: 0 0 0 20px;
}

.header {
  text-align: center;
  color: #003757;
  font-size: 30px;
  padding: 40px 0 0 0;
}

@media screen and (max-width: 767px) {
  .header {
    font-size: 15px;
  }

  .trend-container {
    margin: auto;
    font-size: 20px;
    width: 300px;
    margin-top: 80px;
  }
}
</style>
