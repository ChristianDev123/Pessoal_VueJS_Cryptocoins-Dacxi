<template>
    <section class="grid grid-cols-1">
        <div class="mainCard mb-10 lg:mb-0">
            <MainCard :dataCoin="bitcoinData"/>
        </div>
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-5">
            <div class="py-3 lg:py-10"
                v-for="coins in coinsData"
                :key="coins.id">
                <RowCards :dataCoin="coins"/>
            </div>
        </div>
    </section>
</template>
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
                coinsData:[],
                countId:0
            }
        },
        methods:{
            APIReceiver(){
                fetch("https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&ids=bitcoin%2Ccosmos%2Cethereum%2Cterra-luna&order=market_cap_asc&per_page=3&page=1&sparkline=false")
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
                    currentPrice:data.current_price.toLocaleString('en-US',{style:"currency",currency:'USD'}),
                    datePrice:date
                };
                this.bitcoinData = objBitcoin;
            },
            setAnotherCoinsState(data){
                var date = new Date;
                const month = String(date.getMonth()).length === 1? `0${date.getMonth()+1}`:date.getMonth();
                const hour = String(date.getHours()).length === 1?`0${date.getHours()}`:date.getHours();
                const minutes = String(date.getMinutes()).length === 1?`0${date.getMinutes()}`:date.getMinutes();
                const seconds = String(date.getSeconds()).length === 1?`0${date.getSeconds()}`:date.getSeconds();
                date = `${date.getDate()}/${month}/${date.getFullYear()} ${hour}:${minutes}.${seconds}`
                const objAnotherCoin = {
                    id:this.countId,
                    nameCoin:`Name: ${data.name} Symbol: ${data.symbol}`,
                    currentPrice:data.current_price.toLocaleString('en-US',{style:'currency',currency:'USD'}),
                    datePrice:date
                };
                this.insertAnotherCoinsState(objAnotherCoin);
                this.countId++;
            },
            insertAnotherCoinsState(object){
                if(this.coinsData.length === 3){
                    this.coinsData = [];
                }
                this.coinsData.push(object);
            }
        },
        mounted(){
            this.APIReceiver();
            setInterval(()=>this.APIReceiver(),60000);
        },
    }
</script>