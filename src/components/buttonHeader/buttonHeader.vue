<template>
    <button class="btnHeader">
        <slot></slot>
    </button>
</template>
<style scoped>
    .btnHeader{
        background-image:linear-gradient(to top,#4985b1,#216790);
        width:160px;
        height:40px;
        color:white;
    }
</style>
<script>
export default {
    name:"ButtonHeader"
}
</script>