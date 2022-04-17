<template>
    <hr>
    <section class="grid grid-cols-1 sm:grid-cols-4 justify-center">
        <div class="flex items-center justify-center line">
            <div class="nameSection">
                <h2>Dashboard CryptoCoin</h2>
            </div>
        </div>
        <ListingFooter :dataSection="contactsDev" class='sm:col-span-2' />
        <ListingFooter :dataSection="technologiesUsed" />
    </section>
</template>

<style scoped>
    .nameSection{
        font-size:30px;
        color:var(--primary);
    }
    .line{
        border-right:1px solid var(--line-detail);
        padding-right: 20px;
    }
    hr{
        background:var(--line-detail);
        height:2px;
    }
    section{
        background:var(--footerBackground);
        padding:5px;
    }
    @media screen and (max-width:768px){
        .line{
            border-right:none;
        }
    }
    @media screen and (max-width:500px){
        .nameSection{
            font-size:20px;
        }
        img{
            width:25px;
            height:25px;
        }
    } 
</style>

<script>
import gmailIcon from '../../assets/img/gmailIcon.svg';
import gitHubIcon from '../../assets/img/gitHubIcon.svg';
import linkedinIcon from '../../assets/img/linkedInIcon.svg';

import CSSImage from '../../assets/img/cssIcon.svg';
import tailwindIcon from '../../assets/img/tailwindIcon.svg';
import vueIcon from '../../assets/img/vueIcon.svg';

import ListingFooter from '../ListingFooter/ListingFooter.vue';

export default {
    name:"Footer",
    components:{
        ListingFooter
    },
    data(){
        return{
            contactsDev:{
                nameSection: 'Contacts Developer',
                listing: [
                    {id:1,image:gmailIcon,platform:"Gmail", link:"none",text:"christian.lima999@gmail.com"},
                    {id:2,image:gitHubIcon,platform:"Github", link:"https://github.com/ChristianDev123",text:"github.com/ChristianDev123"},
                    {id:3,image:linkedinIcon,platform:"LinkedIn", link:"https://linkedin.com/in/christian-santana-040821214/",text:"linkedin.com/christian-santana"}
                ]
            },
            technologiesUsed:{
                nameSection:'Technologies',
                listing:[
                    {id:1,text:"CSS3",image:CSSImage},
                    {id:2,text:"Vue3",image:vueIcon},
                    {id:3,text:"Tailwind",image:tailwindIcon},
                ]
            }
        }
    }
}
</script>
