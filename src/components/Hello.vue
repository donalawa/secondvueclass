<template>
    <div>
        <h1>{{ newTitle }}</h1>
        <button @click="changeTitle">Change Title</button>
    </div>
</template>

<script>

import {eventBus} from '../main'

export default {
  props: {
    newTitle: {
      type: String,
      required: true
    }
  },
  data(){
    return {
      title: 'Hello From Child',
      secondName: 'From First Child',
      gobalName: 'Name From Event Bus',
    }
  },
  methods: {
    changeTitle(){
      this.newTitle = 'Title Changed'
      this.$emit('titleChange', this.newTitle);
      this.$emit('secondName', this.secondName)
      eventBus.$emit('globalName', this.gobalName)
    }
  }
}
</script>


<style lang="stylus">

</style>