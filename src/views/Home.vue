<template>
  <div class="home container-fluid">
    <div class="row">
      <div class="col">
        <h1>find your rhythm</h1>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <form class="form-group" @submit.prevent="search">
          <input type="text" placeholder="Search" v-model="query" required><br>
          <button class="btn btn-outline-info btn-sm" type="submit">Submit</button>
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
        query: '',
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

<style scoped>
  h1 {
    color: white
  }

  input {
    color: white
  }
</style>