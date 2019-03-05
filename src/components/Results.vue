<template>
  <div class="row results">
    <div class="col-4">
      <h1>Results</h1>
      <ol>
        <li v-for="song in results" @click="setActiveSong(song)"></li>
      </ol>
    </div>
  </div>

</template>