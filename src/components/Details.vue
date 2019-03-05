<template>
  <div class="shadow details col-6 text-center">
    <h1>{{song.artistName}}</h1>
    <h2>{{song.trackName}}</h2>
    <img :src="song.artworkUrl60.replace(/60x60/g, '500x500')">
    <br>
    <audio class="my-5" controls :src="song.previewUrl" id="source"></audio>
  </div>
</template>

<script>

  export default {
    name: 'Deets',
    props: ['song'],

    data() {
      return {}
    },
    computed: {},
    methods: {}
  }
</script>

<style>

</style>