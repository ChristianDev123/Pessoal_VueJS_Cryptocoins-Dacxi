<template>
    <section class="grid grid-cols-2">
        <div class="flex px-5 items-center">
            <h1>DashBoard Bitcoin Dacxi</h1>
        </div>
        <div class="flex justify-end items-center py-4 px-7">
            <div class="grid grid-cols-1 sm:grid-cols-3">
                <a href="https://www.linkedin.com/in/christian-santana-040821214/" target="_blank" class='px-2'>
                    LinkedIn Dev
                </a>
                <a class='px-2' href="https://github.com/ChristianDev123" target="_blank">
                    GitHub Rep.
                </a>
                <a class='px-2' href="#">
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
        font-weight: 500;
    }
    a:hover{
        color:var(--primary);
        transition:.5s;
    }
    hr{
        background:var(--line-datail);
    }
    h1{
        color:var(--primary);
        font-family:'Square Peg', cursive;
    }
    @media screen and (min-width:300px) {
        h1{
            font-size:21px;
        }
        a{
            font-size:12px;
        }
        a:hover{
            font-size: 14px;
        }
    }
    @media screen and (min-width:440px) {
        h1{
            font-size:29px;
        }
    }
    @media screen and (min-width:550px) {
        h1{
            font-size:38px;
        }
        a{
            font-size:15px;
        }
        a:hover{
            font-size: 18px;
        }
    }
    @media screen and (min-width:640px){
        a{
            font-size:14px;
        }
    }
    @media screen and (min-width:750px){
        a{
            font-size:18px;
        }
        a:hover{
            font-size: 22px;
        }
    }
    @media screen and (min-width:850px) {
        a{
            font-size:18px;
        }
    }
    @media screen and (min-width:1500px) {
        a{
            font-size:25px
        }
        a:hover{
            font-size: 27px;
        }
    }
</style>
<script> 
    export default {
        name:"Header"
    }
</script>