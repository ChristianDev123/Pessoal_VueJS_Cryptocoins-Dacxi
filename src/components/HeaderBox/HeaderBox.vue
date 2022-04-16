<template>
    <section class="grid grid-cols-5">
        <div class="flex px-5 items-center col-span-2">
            <h1>DashBoard Bitcoin Dacxi</h1>
        </div>
        <div class='flex justify-center items-center'>
            <button @click="$emit('theme'),changeTheme()" :class="this.theme?'dark':'light'">
                <img :src="buttonImage" alt="theme selector">
            </button>
        </div>
        <div class="flex justify-end items-center py-4 px-7 col-span-2">
            <div class="grid grid-cols-1 sm:grid-cols-3">
                <a href="https://www.linkedin.com/in/christian-santana-040821214/" target="_blank" class='px-2'>
                    LinkedIn Dev
                </a>
                <a class='px-2' href="https://github.com/ChristianDev123/SPA_Dashboard_Cryptocoins_Dacxi/" target="_blank">
                    GitHub Rep.
                </a>
                <a class='px-2' href="https://dashboard-cryptocoins-dacxi-rd10nh7z1-christiandev123.vercel.app/">
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
    img{
        width:50px;
        background:white;
        border-radius:100%;
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
import moonIcon from '../../assets/img/moonIcon.svg';
import sunIcon from '../../assets/img/sunIcon.svg';
    export default {
        name:"Header",
        emits:['theme'],
        data(){
            return{
                theme:false,
                buttonImage:sunIcon
            }
        },
        methods:{
            changeTheme(){
                this.theme = !this.theme;
                this.buttonImage = this.theme?moonIcon:sunIcon
            }
        }
    }
</script>
