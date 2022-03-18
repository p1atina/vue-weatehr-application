<template>
  <div class="weather-wrapper">
    <ContentHeader/>
    <CitySelector @selectCity="selectCity"/>
    <WeatherList :weatherList="weatherList"/>
  </div>
</template>

<script>
import weatherMixin from "@/mixins/weatehrMixin";
import ContentHeader from "@/components/weather/ContentHeader";
import CitySelector from "@/components/weather/CitySelector";
import WeatherList from "@/components/weather/WeatherList";

export default {
  name: "WeatherContent",
  components: {
    ContentHeader,
    CitySelector,
    WeatherList,
  },
  mixins: [weatherMixin],
  data() {
    return {
      weatherList: [],

    };
  },
  methods: {
    async selectCity(city) {
      if (city.selected) {
        const weather = await this.getWeatherInfo(city);
        console.log(weather, "weather");
        this.weatherList.push(weather);
      } else {
        const index = this.weatherList.findIndex(weather => weather.code === city.code);
        this.weatherList.splice(index, 1);
      }
    },
  },
};
</script>

<style scoped>

</style>