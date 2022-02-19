<template>
  <v-card>
    <hello-world msg="Welcome to Your Vue.js App"/>
  </v-card>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
export default {
  layout: 'default',
  components: {
    HelloWorld
  } 
}
</script>
