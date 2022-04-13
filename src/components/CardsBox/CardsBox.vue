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
                fetch("https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&ids=bitcoin%2Cethereum%2Cterra-luna&order=market_cap_asc&per_page=3&page=1&sparkline=false")
                .then((response)=>response.json())
                .then((json)=>{
                    json.forEach((coin) => {
                        if(coin.id === "bitcoin"){
                            this.setBitcoinState(coin);
                        }else{
                            this.setAnotherCoinsState(coin);
                        }
                    });
                });
            },
            setBitcoinState(data){
                var date = new Date;
                const month = String(date.getMonth()).length === 1? `0${date.getMonth()+1}`:date.getMonth();
                date = `${date.getDate()}/${month}/${date.getFullYear()} ${date.getHours()}:${date.getMinutes()}.${date.getSeconds()}`
                const objBitcoin = {
                    id:1,
                    nameCoin:`Name:${data.name}\n Symbol:${data.symbol}`,
                    currentPrice:data.current_price,
                    datePrice:date
                };
                this.bitcoinData = objBitcoin;
            },
            setAnotherCoinsState(data){
                var date = new Date;
                const month = String(date.getMonth()).length === 1? `0${date.getMonth()+1}`:date.getMonth();
                date = `${date.getDate()}/${month}/${date.getFullYear()} ${date.getHours()}:${date.getMinutes()}.${date.getSeconds()}`
                const objAnotherCoins = [
                    {id:1,nameCoin:`Name: ${data.name} \nSymbol: ${data.symbol}`,currentPrice:data.current_price,datePrice:date},
                    {id:2,nameCoin:`Name: ${data.name} \nSymbol: ${data.symbol}`,currentPrice:data.current_price,datePrice:date},
                    {id:3,nameCoin:`Name: ${data.name} \nSymbol: ${data.symbol}`,currentPrice:data.current_price,datePrice:date}
                ];
                this.coinsData = objAnotherCoins;
            },
        },
        mounted(){
            this.APIReceiver();
            setInterval(()=>this.APIReceiver(),60000);
        },
    }
</script>