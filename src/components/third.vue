<template>
    <div class="red">
        <h1>Red Template</h1>
    </div>
</template>

<script>
export default {
    created(){
        alert('Third Component Was Created')
    }
}
</script>

<style scoped>
    .red {
        width: 400px;
        height: 200px;
        padding: 20px;
        text-align: center;
        background: rosybrown;
    }
</style>