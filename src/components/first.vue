<template>
    <div class="green">
        <h1>Green Template</h1>
        <h1>{{ counter }}</h1>
        <button @click="counter++">Increment</button>
    </div>
</template>

<script>
export default {
    data(){
        return {
            counter: 0
        }
    },
    created(){
        alert('First Component Was Created')
    },
    deactivated(){
        alert('component was Deactivated')
    },
    activated(){
        alert('Compnent Was Activated')
    }
}
</script>

<style scoped>
       .green{
        width: 400px;
        height: 200px;
        padding: 20px;
        text-align: center;
        background: palegreen;
    }
</style>