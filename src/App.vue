<template>
  <h1 class="text-primary">Watchers</h1>

  <h2>Volume Tracker (0-20)</h2>
  <h3>Current Volume => {{ volume }}</h3>
  <div>
    <buttton class="btn btn-primary" @click="volume += 2">+</buttton>
    <buttton class="btn btn-warning" @click="volume -= 2">-</buttton>
  </div>
  <div>
    <input type="text" v-model="movie" />
    <input type="text" v-model="movieInfo.title" />
    <input type="text" v-model="movieInfo.actor" />
  </div>
  <div>
    <button class="btn btn-primary" @click="movieList.push('Wonder Woman')">Add Movie</button>
  </div>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        volume: 0,
        movie: 'Batman',
        movieInfo: {
          title: '',
          actor: '',
        },
        movieList: ['Batman', 'Superman'],
      }
    },

    methods: {},

    computed: {},

    watch: {
      volume(newValue1, oldValue) {
        if (newValue1 > oldValue && newValue1 === 16) {
          alert('Listening to a high volume for a long time may damage your hearing')
        }
      },
      movie: {
        handler(newValue) {
          console.log(`Calling API with new movie name = ${newValue}`)
        },
        immediate: true,
      },
      movieInfo: {
        handler(newValue) {
          console.log(`Calling API with new movie title = ${newValue.title} and actor = ${newValue.actor} `)
        },
        deep: true,
      },
      movieList: {
        handler(newValue) {
          console.log(`Updated list ${newValue}`)
        },
        deep: true,
      },
    },
  }
</script>

<style>
  #app {
    font-family: quicksand, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
    margin-left: 20px;
  }
  div {
    margin: 1rem 0;
  }
</style>
