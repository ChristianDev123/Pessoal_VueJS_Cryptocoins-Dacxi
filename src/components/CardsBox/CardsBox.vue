<template>
    <section class="mainCard">
      <MainCard :dataCoin="bitcoinData"/>
    </section>
    <section
        class="grid grid-cols-1 lg:grid-cols-3"     
    >
        <div
            class="py-3 lg:py-10 px-2"
            v-for="coins in coinsData"
            :key="coins.id"
        >
            <RowCards :dataCoin="coins"/>
        </div>
    </section>
</template>
<style scoped>
    @media screen and (max-width:1024px){
        .mainCard{
            margin-bottom:40px;
        }
    }
</style>
<script>
import MainCard from '../mainCard/mainCard.vue';
import RowCards from '../RowCards/RowCards.vue';
    export default {
        name:"CardsBox",       
        components:{
            MainCard,
            RowCards
        },
        data(){
            return{
                bitcoinData:{},
                coinsData:[
                    {id:0,nameCoin:"Name Coin",currentPrice:"",datePrice:""},
                    {id:1,nameCoin:"Name Coin",currentPrice:"",datePrice:""},
                    {id:2,nameCoin:"Name Coin",currentPrice:"",datePrice:""}
                ]
            }
        },
        methods:{
            APIReceiver(){
                fetch("https://api.coingecko.com/api/v3/simple/price?ids=bitcoin%2Cethereum%2Ccosmos%2Cterra-luna&vs_currencies=usd&include_last_")
                .then((response)=>response.json())
                .then((json)=>console.log(json))
            }
        },
        mounted(){
            this.APIReceiver();
        },
    }
</script>