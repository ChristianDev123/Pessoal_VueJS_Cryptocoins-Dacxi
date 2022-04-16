<template>
    <hr>
    <section class="grid grid-cols-1 sm:grid-cols-4 justify-center">
            <div class="flex items-center justify-center line">
            <div class="nameSection">
                <h2>Dashboard CryptoCoin</h2>
            </div>
        </div>
        <div class="flex flex-col sm:col-span-2 justify-center items-center line">
            <div class="nameSection py-2">
                <h2>Contacts Developer</h2>
            </div>
            <div class="list">
                <ul>
                    <li v-for="contact in contactsDev" :key="contact.id" >
                        <a :href="contact.link">
                            <div class="flex gap-5">
                                <img :src="contact.image" :alt="contact.platform"/>
                                <p>{{contact.text}}</p>
                            </div>
                        </a>
                    </li>
                </ul>
            </div>
        </div>
        <div class="flex flex-col justify-center items-center">
            <div class="nameSection py-2">
                <h2>Technologies</h2>
            </div>
            <div class="list">
                <ul>
                    <li v-for="tecnology in technologiesUsed" :key="tecnology.id">
                        <div class="flex gap-5">
                            <img :src="tecnology.image" :alt="tecnology.name + ' image'">
                            <p>{{tecnology.name}}</p>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </section>
</template>

<style scoped>
    img{
        height:45px;
        width:45px;
    }
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

export default {
    name:"Footer",
    data(){
        return{
            contactsDev:[
                {id:1,image:gmailIcon,platform:"Gmail", link:"#",text:"christian.lima999@gmail.com"},
                {id:2,image:gitHubIcon,platform:"Github", link:"https://github.com/ChristianDev123",text:"github.com/ChristianDev123"},
                {id:3,image:linkedinIcon,platform:"LinkedIn", link:"https://linkedin.com/in/christian-santana-040821214/",text:"linkedin.com/christian-santana"}
            ],
            technologiesUsed:[
                {id:1,name:"CSS3",image:CSSImage},
                {id:2,name:"Vue3",image:vueIcon},
                {id:3,name:"Tailwind",image:tailwindIcon},
            ]
        }
    }
}
</script>
