<template>
  <div>
    <div class="searchResult">
      <p v-if="searchResult.length <= 0">No result</p>
      <div v-for="(result, i) in searchResult.results" :key="i"> 
        <movie-card :info="result"></movie-card>
      </div>
    </div>
  </div>
</template>

<script>
  import MovieCard from './MovieCard.vue'

  export default {
    computed: {
      searchResult() {
        return this.$store.state.searchResult;
      }
    },
    components: {
      MovieCard
    }
  }
</script>

<style >
  .searchResult {
    text-align: center;
  }
</style>

