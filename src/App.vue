<template>
    <div id="app">
        <h1>{{ title }}</h1>
        <input type="text" v-model="title">
        <ul>
          <li v-for="(person,index) in persons" :key="index">{{ person }}</li>
        </ul>
        <button class="btn btn-primary">Change</button>
       <div class="parent">
          <div class="first">
           <app-hello v-on:titleChange="title = $event" v-on:secondName="secondName = $event" v-bind:newTitle="title"></app-hello>
        </div>
       
        <div class="second">
            <app-second :newName="secondName">
              <h1 slot="first">This is a slot</h1>
              <h2 slot="second">Second Slot</h2>
            </app-second>
        </div>
       </div>

       <button @click="currentComponent = 'first'">Green Template</button>
       <button  @click="currentComponent = 'third'">Red Template</button>
       <button  @click="currentComponent = 'fourth'">Purple Template</button>
       <keep-alive>
          <component :is="currentComponent"></component>
       </keep-alive>
    </div>
</template>

<script>
import  Hello  from './components/Hello.vue';
import Second from './components/Second.vue';
import first from './components/first.vue';
import third from './components/third.vue';
import fourth from './components/fourth.vue';

export default {
  data(){
    return {
      title: 'Value Comming From Props',
      persons: ['Jhon','Fred','James','Mark','Max','Doe'],
      inputName: '',
      secondName: '',
      currentComponent: 'first'
    }
  },
  name: 'app',
  components: {
    'app-hello': Hello,
    'app-second': Second,
    first,
    third,
    fourth
  },
}
</script>


<style scoped>
  h1 {
    color: red;
  }

  .parent {
    display: flex;
  }

  button {
    background: teal;
    padding: 10px;
    margin-bottom: 100px;
  }

  .first {
    width: 300px;
    height: 300px;
    background: palegreen;
    padding: 10px;
    text-align: center;
  }

    .second {
    width: 300px;
    height: 300px;
    background: rosybrown;
    margin-left: 20px;
    padding: 10px;
    text-align: center;
  }



</style>