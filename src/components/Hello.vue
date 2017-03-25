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
import Vue from 'vue'

export default {
  name: 'hello',
  data () {
    return {
      beersCount: 10000
    }
  },
  methods: {
    beerPurchased: function() {
      this.beersCount = this.beersCount - 1;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
