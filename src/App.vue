<template>
  <div class="app">
    <div class="header container h-100 p-5">
      <h1 class="mb-5">Weather App</h1>
      <div class="d-flex justify-content-center h-100">
        <div class="searchbar w-50 mx-2">
          <input type="text" class="input form-control" v-model="city" placeholder="Enter City/Town">
        </div>
        <button class="btn-search btn btn-primary">Search <i class="fas fa-search"></i></button>
      </div>
    </div>
    <br>
    <weather></weather>
  </div>
</template>

<script>

import weather from './components/weather.vue';

export default {
  name: "App",
  components: {
    weather
  },
  data() {
    return {
      city:"",
      showWeather:false,
    }
  },
  methods: {
    async searchWeather(){
      this.showWeather=false;
      await this.$nextTick();
      this.showWeather=true;
    }
  },
};
</script>

<style>
body{
  background-color: #0e0e0f;
}
.header{
  background-color:#212730;
  border-radius: 20px;
  color: #fff;
  text-align: center;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  margin-top: 5rem;
}
.btn-search{
  background-image: linear-gradient(to right, cyan ,magenta);
}
</style>
