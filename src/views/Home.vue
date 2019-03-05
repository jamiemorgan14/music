<template>
  <div class="home container-fluid">
    <div class="row">
      <div class="col">
        <h1>Mustache Music</h1>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <form class="form-group" @submit.prevent="search">
          <input type="text" placeholder="Search" v-model="query" required>
          <button class="btn btn-outline-info" type="submit">Submit</button>
        </form>
      </div>
    </div>
    <results></results>
  </div>
</template>

<script>
  import Results from '@/components/Results.vue'


  export default {
    name: 'home',
    data() {
      return {
        query: ''
      }
    },

    computed: {

    },
    methods: {
      search() {
        this.$store.dispatch('getSongByArtist', this.query)
      }
    },
    components: {
      Results
    }
  }
</script>