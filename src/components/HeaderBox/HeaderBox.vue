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
                <ButtonHeader v-for="button,index in dataLinks" :key="index"  :dataButton="button"/>
            </div>
        </div>
        <hr>
    </section>
</template>
<style scoped>
    hr{
        background:var(--line-detail);
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
import ButtonHeader from '../ButtonHeader/ButtonHeader.vue';
    export default {
        name:"Header",
        emits:['theme'],
        data(){
            return{
                theme:false,
                buttonImage:sunIcon,
                dataLinks:[
                    {text:'LinkedIn Dev', link:'https://www.linkedin.com/in/christian-santana-040821214/'},
                    {text:'GitHub Rep.', link:'https://github.com/ChristianDev123/SPA_Dashboard_Cryptocoins_Dacxi/'},
                    {text:'Vercel Deploy', link:'https://dashboard-cryptocoins-dacxi-rd10nh7z1-christiandev123.vercel.app/'}
                ]
            }
        },
        components:{
            ButtonHeader
        },
        methods:{
            changeTheme(){
                this.theme = !this.theme;
                this.buttonImage = this.theme?moonIcon:sunIcon
            }
        }
    }
</script>
