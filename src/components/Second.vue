<template>
    <div>
        <slot name="first"></slot>
        <h1>{{ title }}</h1>
        <h2>{{ newName }}</h2>
        <h3>{{ name }}</h3>
        <slot name="second">Second Default</slot>
    </div>
</template>

<script>
import {eventBus} from '../main'
export default {
  props: ['newName'],
  data(){
    return {
      title: 'Hello From Second Child',
      name: ''
    }
  },

  created() {
      eventBus.$on('globalName', (nname) => {
          this.name = nname;
      })
  }
 
}
</script>


<style scoped>
    h1 {
        color: blue;
    }
</style>