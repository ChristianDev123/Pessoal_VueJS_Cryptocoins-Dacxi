<template>
    <div class="mx-auto px-4 py-4 rounded-md" id="mainCard">
        <div class="flex flex-col justify-center image">
            <img :src="image" alt="BitCoin Image">
            <h2 class="text-center">{{dataBitcoin.nameCoin}}</h2>    
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 ">
            <div class="mx-auto">
                <div class="showData">
                    <p><span class='label'>Current Price (USD):</span> {{dataBitcoin.currentPrice}}</p>
                    <p><span class='label'>Date Price:</span> {{dataBitcoin.date}}</p>
                    <span class='ps'>(Brasilia, Brazil Time Zone)</span>
                </div>
                <div class="showData">
                    <p class="py-4">Insert a date to view price:</p>
                    <form @submit="submitHandler($event)">
                        <div class='text-center dateWrapper'>
                            <input class="dateInput" type="date" required>
                        </div>
                        <div class="py-4 flex flex-col sm:flex-row gap-3">
                            <input type="submit" value="Send">
                            <input type="button" value="Current" @Click="intervalWrapper('start')">
                        </div>
                    </form>
                </div>
            </div>
            <div class="flex items-end justify-center">
                <img :src="tinyimage" class='hidden sm:inline tinyImage' alt="Little Image Bitcoin">
            </div>
        </div>
    </div>
</template>
<style scoped>
    #mainCard{
        box-shadow: 5px 5px 15px rgba(0,0,0,0.8);
    }
    .showData{
        color:var(--primary);
        font-size:20px;
    }
    .dateInput{
        border:2px solid var(--primary);
        padding:0 5px;
    }
    span.ps{
        font-size:10px;
    }
    input[type="submit"],input[type="button"]{
        border:2px solid var(--primary);
        padding:0px 30px;
    }
    input[type="submit"]:hover,input[type="button"]:hover{
        color:white;
        padding:2px 37px;
        background:var(--primary);
        transition:.7s;
        border-radius:10px;
    }
    @media screen and (min-width:300px) {
        .showData{
            font-size:12px;
        }
        .image{
            font-size:8px;
        }
    }
    @media screen and (min-width:600px) {
        .showData{
            font-size:17px;
        }
        .image{
            padding:5px;
            font-size:10px;
        }
    }
    @media screen and (min-width:800px){
        .image{
            padding:25px;
            font-size:12px;
            color:var(--primary);
        }
        .dateWrapper{
            text-align:left;
        }
    }
    .tinyImage{
        width:170px;
        height:200px;
        border-radius:10px;
    }
</style>
<script>
import imageBitcoin from '../../assets/img/bitcoinImage.png';
import tinyImageBitcoin from '../../assets/img/tinyImageBitcoin.jpg'
    export default {
        name:"MainCard",
        data(){
            return{
                image:imageBitcoin,
                tinyimage:tinyImageBitcoin,
                dataBitcoin:{
                    currentPrice:'',
                    date:'',
                },
                dataPerDateTime:[],
                viewer:'',
            }
        },
        props:{
            dataCoin:Object
        },
        mounted(){
            this.intervalWrapper("start");
        },
        methods:{
            submitHandler(event){
                event.preventDefault();
                const inputsValues = document.querySelectorAll('.dateInput');
                const objDateTime = {
                    date:inputsValues[0].value,
                }
                this.dataPerDateTime = objDateTime;
                this.intervalWrapper('stop');
                this.apiPerDatetime();
            },
            insertDataState(coin,date='',price=0){
                const objectBitcoin = {
                    nameCoin:'Name: bitcoin Symbol: btc',
                    currentPrice: price || coin.currentPrice,
                    date:date || coin.datePrice 
                }
                this.dataBitcoin = objectBitcoin
            },
            intervalWrapper(command){
                if(command==="start"){
                    this.viewer = setInterval(()=>this.insertDataState(this.dataCoin),2000);
                }else{
                    clearInterval(this.viewer);
                    this.viewer = false;
                }
            },
            apiPerDatetime(){
                const dateArray = this.dataPerDateTime.date.split('-');
                dateArray.reverse();
                const strDate = dateArray.reduce((ac,nv)=> `${ac}-`+nv);
                if(!this.viewer){
                    const url = `https://api.coingecko.com/api/v3/coins/bitcoin/history?date=${strDate}&localization=false`;
                    fetch(url)
                    .then((response)=>response.json())
                    .then(({market_data})=>this.insertDataState(market_data,dateArray.reduce((ac,nv)=>`${ac}/`+nv), market_data.current_price.usd.toLocaleString('en-US',{style:"currency",currency:'USD'})));
                }
            }
        },
    }
</script>