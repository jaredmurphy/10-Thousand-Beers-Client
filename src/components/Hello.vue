<template>
  <div>
    <div class="beers">
      <h1>{{ beersCount }}</h1>
      <h2>Beers Left</h2>
    </div>
    <div class="button">
      <button v-on:click="beerPurchased()">Beer Purchased</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  apiUrl: 'http://localhost:9292/beers',
  data () {
    return {
      beersCount: "...Loading"
    }
  },
  methods: {
    beerPurchased: function() {
      fetch('http://localhost:9292/purchase_beer', {method: 'POST'})
        .then(data => data.json())
        .then(beers => {
          this.updateBeers(beers[0].count)
        })
    },
    fetchBeers: function() {
      console.log('fetch beer')
      fetch('http://localhost:9292/beers')
        .then(data => data.json())
        .then(beers => {
          this.updateBeers(beers[0].count)
        })
    },
    updateBeers: function(count) {
      this.beersCount = count;
    }
  },
  beforeMount: function() {
    this.fetchBeers()
  }
}


</script>

<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
