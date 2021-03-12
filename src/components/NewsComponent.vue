<template>
  <div>
      <div class="col-xl-12 col-lg-12 col-md-12 col-sm-12 col-xs-12">
      <button type="button" class="btn btn-secondary btn-block" v-on:click="callBackend('top-news')">Top News</button>
      <button type="button" class="btn btn-secondary btn-block" v-on:click="callBackend('stock-market')">Stock Market News</button>
      <button type="button" class="btn btn-secondary btn-block" v-on:click="callBackend('commodities')">Commodities News</button>
      <button type="button" class="btn btn-secondary btn-block" v-on:click="callBackend('ipo-fpo')">IPO/FPO News</button>
      <button type="button" class="btn btn-secondary btn-block" v-on:click="callBackend('mutual-funds')">Mutual funds News</button>
      </div>
    <ul>
      <li v-for="(item,index) in info" :key="index">
        <a target= "_blank" :href= "item.url"> {{ item.title }}   </a>
  </li><hr>
</ul>
</div>
</template>

<script>
import axios from 'axios';
export default {
name: 'NewsComponent',
 data() {
    return {
      info: null
    };
},
methods : {
callBackend : function (routeName) {
 axios.get("https://python-flask-news-api.herokuapp.com/"+ routeName)
 .then(response => this.info = response.data);
}
},

  created() {
    // Simple GET request using axios
    axios.get("https://python-flask-news-api.herokuapp.com/top-news")
      .then(response => this.info = response.data);
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
button {
  margin-right: 15px;
}
li{
  margin: 10px 0;
}

a {
  color: #42b983;
}
</style>
