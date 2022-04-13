<template>
    <section class="
        flex
        flex-row
        justify-end
        py-4
        ">
        <div class="
            flex
            flex-wrap
            gap-7
        ">
            <a href="" >
                LinkedIn Dev
            </a>
            <a href="">
                GitHub Rep.
            </a>
            <a href="">
                Vercel Deploy
            </a>
        </div>
    </section>
    <hr>
</template>
<style scoped>
    a{
        color:#808080;
        font-size:20px;
        font-weight: 500;
    }
    a:hover{
        color:var(--primary);
        font-size:22px;
    }
    hr{
        background:var(--line-datail);
    }
</style>
<script> 
    export default {
        name:"Header",
        components:{
        }
    }
</script>