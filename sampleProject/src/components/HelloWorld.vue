<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li>
<!-- <video autoplay="autoplay" loop="loop" muted="muted" webkit-playsinline="webkit-playsinline" playsinline="playsinline"> -->
      <video autoplay="autoplay" loop="loop" muted="muted" playsinline="playsinline"> 
        <source src="http://mulawear.jpg3.kr//phps/video/main.mp4" type="video/mp4">
      </video>
      </li>
      <li>
        <a
          href="https://forum.vuejs.org"
          target="_blank"
        >
          Forum
        </a>
      </li>
      <li>
        <a
          href="https://chat.vuejs.org"
          target="_blank"
        >
          Community Chat
        </a>
      </li>
      <li>
        <a
          href="https://twitter.com/vuejs"
          target="_blank"
        >
          Twitter
        </a>
      </li>
      <br>
      <li>
        <a
          href="http://vuejs-templates.github.io/webpack/"
          target="_blank"
        >
          Docs for This Template
        </a>
      </li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li>
        <a
          href="http://router.vuejs.org/"
          target="_blank"
        >
          vue-router
        </a>
      </li>
      <li>
        <a
          href="http://vuex.vuejs.org/"
          target="_blank"
        >
          vuex
        </a>
      </li>
      <li>
        <a
          href="http://vue-loader.vuejs.org/"
          target="_blank"
        >
          vue-loader
        </a>
      </li>
      <li>
        <a
          href="https://github.com/vuejs/awesome-vue"
          target="_blank"
        >
          awesome-vue
        </a>
      </li>
      <button v-on:click="onButton()">sample button</button>
      <label name="label_1"> {{ this.apiResultMsg }} </label>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: '  TTTT BB '
      , apiResultMsg:''
    }
  },
  methods:{
    onButton(){
      console.log('called Button')
      

    axios({
      method: 'get',
      url: 'http://localhost:8081/test/demo',
      headers: { 'Accept': '*/*',  }
    })
      .then(function (response) {
        this.apiResultMsg = reponse.data
      })
        // axios.get('https://jsonplaceholder.typicode.com/todos?_limit=10')
        //     .then(res => this.apiResultMsg = res.data)
        //     .catch(error => console.error(error))
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
