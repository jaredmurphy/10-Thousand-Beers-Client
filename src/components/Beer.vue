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
  name: 'beer',
  data () {
    return {
      beersCount: "...Loading"
    }
  },
  methods: {
    beerPurchased: function() {
      fetch('https://radiant-crag-18740.herokuapp.com/purchase_beer', {method: 'POST'})
        .then(data => data.json())
        .then(beers => {
          this.updateBeers(beers[0].count)
        })
    },
    fetchBeers: function() {
      fetch('https://radiant-crag-18740.herokuapp.com/beers')
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

</style>
