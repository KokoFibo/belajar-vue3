<template>
  <h1 class="text-primary">Computed Properties</h1>
  <h2>Fullname - {{ firstName }} {{ lastName }}</h2>
  <h2>Computed Fullname - {{ fullName }}</h2>
  <button @click="changeFullname" class="btn btn-primary">Change fullname</button>
  <div class="my-3"><input type="number" v-model.number="a" /> X <input type="number" v-model.number="b" /> = {{ c }}</div>
  <div class="my-2">
    <button @click="items.push({ id: 4, title: 'keyboard', price: 50 })">Add Item</button>
  </div>
  <h2>Computed Total - {{ total }}</h2>
  <h2>Method Total - {{ getTotal() }}</h2>
  <input type="text" v-model="country" />
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        firstName: 'Bruce',
        lastName: 'Wayne',
        a: null,
        b: null,
        items: [
          {
            id: 1,
            title: 'TV',
            price: 100,
          },
          {
            id: 2,
            title: 'Phone',
            price: 200,
          },
          {
            id: 3,
            title: 'Laptop',
            price: 300,
          },
        ],
        country: '',
      }
    },
    methods: {
      getTotal() {
        console.log('getTotal Method')
        return this.items.reduce((total, curr) => (total += curr.price), 0)
      },
      changeFullname() {
        this.fullName = 'Clark Kent'
      },
    },
    computed: {
      fullName: {
        get() {
          return `${this.firstName} ${this.lastName}`
        },

        set(value) {
          const names = value.split(' ')
          this.firstName = names[0]
          this.lastName = names[1]
        },
      },

      c() {
        return this.a * this.b
      },

      total() {
        console.log('Total computed property')
        return this.items.reduce((total, curr) => (total += curr.price), 0)
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
</style>
