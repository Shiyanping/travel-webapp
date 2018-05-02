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
import CityHeader from './components/CityHeader';
import CitySearch from './components/Search';
import CityList from './components/List';
import CityAlphabet from './components/Alphabet';
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
