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
        <div>
            <h2 class='text-center py-2'> Bitcoin's price in an interval of three days</h2>
            <div id='chartWrapper'>
                <ChartBitcoin :dataBitcoin="bitcoinDataLastThreedays"/>
            </div>
        </div>
    </section>
</template>
<style scoped>
    #chartWrapper{
        background: whitesmoke;
        border-radius:10px;
        padding:5px;

    }
</style>
<script>
import MainCard from '../mainCard/mainCard.vue';
import RowCards from '../RowCards/RowCards.vue';
import ChartBitcoin from '../ChartBitcoin/ChartBitcoin.vue';
    export default {
        name:"CardsBox",       
        components:{
            MainCard,
            RowCards,
            ChartBitcoin
        },
        data(){
            return{
                bitcoinData:{},
                coinsData:[],
                bitcoinDataLastThreedays:[],
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
            },
            APIReceiverChart(){
                fetch("https://api.coingecko.com/api/v3/coins/bitcoin/market_chart?vs_currency=usd&days=3&interval=daily")
                .then((response)=>response.json())
                .then((json)=>{
                    this.tratamentDataChart(json.prices);
                })
            },
            tratamentDataChart(coinData){
                const dates = coinData.map((coins)=>{
                    const d = new Date(coins[0])
                    return d.toLocaleDateString()
                });
                const prices = coinData.map((coins)=>coins[1].toFixed(2));
                
                this.bitcoinDataLastThreedays = {
                    labels:dates,
                    datasets:[{
                        label: 'Price Bitcoin',
                        backgroundColor: '#216190',
                        borderColor:'rgba(33,97,144,0.75)',
                        data:prices,
                        borderWidth:3
                    }]
                }
            }
        },
        created(){
            this.APIReceiver();
            setInterval(()=>this.APIReceiver(),60000);
            this.APIReceiverChart();
        },
    }
</script>