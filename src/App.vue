<template>
  <div id="app">
    <ul class="nav">
      <li class="nav-item">
        <router-link :to="{ name: 'HelloWorld' }" class="nav-link active">地点検索</router-link>
      </li>
      <li class="nav-item">
        <router-link :to="{ name: 'Direction' }" class="nav-link" href="#">行き方</router-link>
      </li>
    </ul>
    <h1>埋め込み Google Map Generator</h1>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
