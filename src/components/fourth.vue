<template>
    <div class="purple">
        <h1>Purple Template</h1>
    </div>
</template>

<script>
export default {
     created(){
        alert('Fourth Component Was Created')
    }
}
</script>

<style scoped>
           .purple {
        width: 400px;
        height: 200px;
        padding: 20px;
        text-align: center;
        background: purple;
        color: white;
    }
</style>