<template>
    <a class='px-2' :href="dataButton.link">
        {{dataButton.text}}
    </a>
</template>
<style scoped>
    a{
        color:#808080;
        font-weight: 500;
    }
    a:hover{
        transition:.5s;
    }
</style>
<script>
    export default {
        name:'ButtonHeader',
        props:['dataButton']
    }
</script>