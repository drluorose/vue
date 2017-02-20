<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://gitter.im/vuejs/vue" target="_blank">Gitter Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
      <br>
      <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <button @click="show">这里的button</button>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
      <li>
        <Icon size='10' color='#42b983' type="ios-lightbulb-outline" slot="icon"></Icon>
      </li>
      <li>
        <Alert v-bind:show-icon='true' v-bind:closable='true'>消息提示文案</Alert>
      </li>
      <li>
        <Alert ref="alert" v-bind:show-icon='true' v-bind:closable='true'>
          自定义图标
          <Icon type="ios-lightbulb-outline" slot="icon"></Icon>
          <template slot="desc">自定义图标文案自定义图标文案自定义图标文案自定义图标文案自定义图标文案</template>
        </Alert>
      </li>
    </ul>
    <div>
      <Alert type="warning" show-icon>
        警告提示文案
        <template slot="desc">
          警告的提示描述文案警告的提示描述文案警告的提示描述文案
        </template>
      </Alert>
    </div>

  </div>

</template>

<script>
import Icon from './icon'
import Alert from './alert'
export default {
  name: 'hello',
  components: { Icon , Alert},
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      showAlert:true
    }
  },
   methods: {
    show: function (event) {
      let alert =  this.$refs.alert;
      if(alert.isClosed()){
        alert.show()
      }else{
        alert.close()
      }
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
