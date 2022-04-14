<template>
    <section class="grid grid-cols-2">
        <div class="flex px-5 items-center">
            <h1>DashBoard Bitcoin Dacxi</h1>
        </div>
        <div class="flex justify-end items-center py-4 px-7">
            <div class="grid grid-cols-1 sm:grid-cols-3">
                <a href="https://www.linkedin.com/in/christian-santana-040821214/" class='px-2'>
                    LinkedIn Dev
                </a>
                <a class='px-2' href="https://github.com/ChristianDev123">
                    GitHub Rep.
                </a>
                <a class='px-2' href="">
                    Vercel Deploy
                </a>
            </div>
        </div>
        <hr>
    </section>
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
    h1{
        font-size:50px;
        color:var(--primary);
        font-family:'Square Peg', cursive;
    }
    @media screen and (max-width:700px){
        h1{
            font-size:32px;
        }
    }
    @media screen and (max-width:500px) {
        a{
            font-size:12px;
        }
        h1{
            font-size:20px;
        }
    }
    @media screen and (max-width:300px) {
        h1{
            font-size:15px;
        }
        a{
            font-size:8px;
        }
    }
</style>
<script> 
    export default {
        name:"Header",
        components:{
        }
    }
</script>