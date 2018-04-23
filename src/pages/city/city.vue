<template>
  <div id="container">
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list :cities="cities" :hot="hotCities" :letter="letter"></city-list>
    <city-alphabet :cities="cities" @change="changeAlpabet"></city-alphabet>
  </div>
</template>

<script>
import axios from 'axios';
import CityHeader from './components/cityHeader';
import CitySearch from './components/search';
import CityList from './components/list';
import CityAlphabet from './components/alphabet';
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data() {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    };
  },
  methods: {
    getCityList() {
      axios.get('/api/city').then(this.getCityListSucc);
    },
    getCityListSucc(res) {
      if (res.data.code === 200) {
        const data = res.data.data;
        this.cities = data.cities;
        this.hotCities = data.hotCities;
      }
    },
    changeAlpabet(letter) {
      this.letter = letter;
    }
  },
  mounted() {
    this.getCityList();
  }
};
</script>

<style lang="stylus"></style>
