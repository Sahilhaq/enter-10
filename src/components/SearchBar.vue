<template>
  <div class="container">
    <div class="search-box" id="SBox">
      <input id="search" placeholder="Search..." type="text" @keyup.enter="searchApi" v-model="search_query">
      <div class="also search-link" @click="searchApi" id="searchclick"></div>
      <select class="fa fa-cog also select-type" v-model="selected">
        <option value="movie">Movie</option>
        <option value="tv">TV</option>
      </select>
    </div>
    <div class="searchResultArea">

    </div>
    <search-result></search-result>
  </div>
</template>

<script>
  const config = require('./../../static/config')
  import searchResult from './SearchResult.vue'

  export default {
    data() {
      return {
        selected: 'movie',
        search_query: ''
      }
    },
    computed: {
      counter() {
        return this.$store.state.counter;
      }
    },
    methods: {
      searchApi() {
        console.log('searching ' + this.search_query)
        this.$http.get(`https://api.themoviedb.org/3/search/${this.selected}?api_key=${config.API_KEY}&language=en-US&page=1&include_adult=false&query=${this.search_query}`).then(response => {
          console.log(response)
          this.$store.state.searchResult = response.body;
        }, error => {
          console.log(error)
        })
      }
    },
    components: {
      searchResult
    }
  }
</script>

<style>
  .searchResultArea {
    margin-top: 100px;
  }
</style>


