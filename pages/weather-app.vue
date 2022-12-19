<template>
  <v-container>
    <h1 class="display-1 mb-3 text-center">Weather App</h1>
    <v-flex xs12>
      <v-card class="blue-gray darken-1" dark>
        <v-card-text>{{city}}</v-card-text>

        <h3>Humidity:{{weather.main.humidity}}</h3>
        <h3>Pressure:{{weather.main.pressure}}</h3>
        <h3>Max Temperature:{{Math.round(weather.main.temp_max-273)}}</h3>
      </v-card>
    </v-flex>
    <v-flex xs12 class="mt-4">
      <v-form @submit.prevent="getWeatherInfo">
        <v-text-field label="Enter your city name" v-model="city"></v-text-field>
      </v-form>
    </v-flex>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      city: "London",
      weather: {}
    };
  },
  created() {
    this.getWeatherInfo();
  },
  asyncData({ params, $axios }) {
    return $axios
      .$get(
        `https://api.openweathermap.org/data/2.5/weather?q=London&appid=${process.env.weatherAppId}`
      )
      .then(res => {
        return {
          weather: res
        };
      });
  },
  methods: {
    getWeatherInfo() {
      this.$axios
        .$get(
          `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=${process.env.weatherAppId}`
        )
        .then(res => (this.weather = res));
    }
  }
};
</script>

<style>
</style>