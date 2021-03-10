<template>
  <div id="app">
    <img alt="finance samachar logo" src="./assets/fs_logo.png">
    <p>  The latest business, finance, mutual funds and stock market news from the last 48 hours from major Indian news sources aggregated in one place. </p>
    <ul>
      <li>
        <a href="https://play.google.com/store/apps/details?id=com.theviralappshub.financesamachar" target="_blank">
          <img src="https://pulse.zerodha.com/images/android.svg" alt="Google playstore" title="Google playstore">
          </a>
      </li>
    </ul>
    <NewsComponent />
  </div>
</template>

<script>
import NewsComponent from './components/NewsComponent.vue'

export default {
  name: 'App',
  components: {
    NewsComponent
  }
}
</script>

<style>
  ul
{
    list-style-type:none;
    padding:0px;
    margin:0px;
}

p {
margin-left: 650px;
width : 30%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
