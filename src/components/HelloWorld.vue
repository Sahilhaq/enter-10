<template>
  <div class="container">
    <p>Counter is: {{ counter }}</p>
    <button @click="increment">increse</button>
    <button @click="decrement">decrese</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      apiKey: 'b6feb8b95705ac9e171a770c50343782',
      sampleData: {
        msg: 'empty'
      },
      imgData: null,
      searchResult: [],
      serchTerm: 'panda',
      searchTypes: ['movie', 'tv'],
      searchType: 0
    }
  },
  computed: {
    counter() {
      return this.$store.state.counter;
    }
  },
  mounted() {
    // this.toAPI()
    this.searchAPI()
  },
  methods: {
    toAPI() {
      this.$http.get(`https://api.themoviedb.org/3/movie/550?api_key=${this.apiKey}`).then(response => {
        console.log(response)
        this.sampleData = response.body;
        this.sampleData.msg = '1 entry'
        // this.getImages()
      }, error => {
        console.log(error)
      })
    },
    searchAPI() {
      this.$http.get(`https://api.themoviedb.org/3/search/${this.searchTypes[this.searchType]}?api_key=${this.apiKey}&language=en-US&page=1&include_adult=false&query=${this.serchTerm}`).then(response => {
        console.log(response)
        this.searchResult= response.body;
      }, error => {
        console.log(error)
      })
    },
    getImages() {
      console.log(this.sampleData)
      this.$http.get(`https://api.themoviedb.org/3/movie/${this.sampleData.id}/images?api_key=${this.apiKey}&language=en-US`).then(response => {
        // console.log(response)
        this.imgData = response.body;
      }, error => {
        console.log(error)
      })
    },
    increment() {
      this.$store.state.counter++
    },
    decrement() {
      this.$store.state.counter--
    }
  }
}
</script>
