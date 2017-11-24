<template>
  <div class="hello">
    <div id="example-1">
      <div>
      from: <input type="text" v-model="from" placeholder="Shinjuku, Japan" />
      </div>
      <div>
      to: <input type="text" v-model="to" placeholder="Kamakura, Japan" />
      </div>
    </div>

    <iframe
      :width="width"
      :height="iframe_data.height"
      frameborder="0"
      style="border:0"
      :src="url"
      allowfullscreen>
    </iframe>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      iframe_data: {
        width: 600,
        height: 450
      },
      counter: 0,
      from: 'Shinjuku, Japan',
      to: 'Kamakura, Japan',
      msg: 'Welcome to Your Vue.js App'
    }
  },
  computed: {
    url () {
      return 'https://www.google.com/maps/embed/v1/directions?key=' + process.env.GOOGLE_MAP_KEY + '&origin=' + this.from +
             '&destination=' + this.to +
             '&mode=walking'
    },
    width () {
      if (window.screen.width < 600) {
        return window.screen.width - 20
      }

      return this.iframe_data.width
    },
    embed_html () {
      var html = '<iframe width=' + this.width + ' ' +
               'height=' + this.iframe_data.height + ' ' +
               'frameborder="0"' + ' ' +
               'style="border:0"' + ' ' +
               'src=' + this.url + ' ' +
               'allowfullscreen></iframe>'
      return html
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
