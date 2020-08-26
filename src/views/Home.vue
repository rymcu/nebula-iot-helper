<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/Main.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  mounted() {
    const ipcRenderer = window.electron.ipcRenderer
    ipcRenderer.send('receiving-broadcast')
    ipcRenderer.on('broadcast-reply', (event, arg) => {
      console.log(arg)
    })
  }
}
</script>
