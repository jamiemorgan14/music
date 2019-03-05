<template>
  <div class="row results">
    <div class="col-6 text-center">
      <h1 class="shadow" v-if="results.length > 0">Results</h1>
      <div class="result-box">
        <ul class="shadow mr-5">
          <li v-for="song in results" @click="setActiveSong(song)"> {{song.artistName}} :
            {{song.trackName}}</li>
        </ul>
      </div>
    </div>
    <deets :song='activeSong'></deets>
  </div>
</template>

<script>
  //import details view
  import Deets from '@/components/Details.vue'
  export default {
    name: '',
    data() {
      return {
        activeSong: {}
      }
    },

    computed: {
      results() {
        let songs = this.$store.state.results;
        return songs.filter(s => s.kind == 'song')
      }
    },
    methods: {
      setActiveSong(song) {
        this.activeSong = song
      }
    },
    components: {
      Deets
    }
  }

</script>

<style>
  * {
    background-image: url(https://images.unsplash.com/uploads/1412282232015a06e258a/4bdd2a58?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2250&q=80);
    background-position: center;
    background-attachment: fixed;
    background-size: 100vh
  }

  .shadow {
    color: white;
    text-shadow: 0 0 5px silver;
    list-style-type: none
  }

  .result-box {
    height: 50vh;
    overflow-y: auto;
    color: white;
    width: 500px;
    margin-left: 160px
  }
</style>