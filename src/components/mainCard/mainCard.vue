<template>
    <div class="container mx-auto px-4 py-4 rounded-md" id="mainCard">
        <div class="flex flex-col justify-center image">
            <img :src="image" alt="BitCoin Image">    
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 ">
            <div class="mx-auto">
                <div class="showData">
                    <p>Current Price (USD): {{dataBitcoin.currentPrice}}</p>
                    <p>Date Price: {{dataBitcoin.date}}</p>
                </div>
                <div class="showData">
                    <p class="py-4">Insert a date to view price:</p>
                    <form @submit="submitHandler($event)">
                        <div class="flex flex-wrap gap-3">
                            <input class="dateInput" type="date" id="">
                            <input class="dateInput" type="time" id="">
                        </div>
                        <div class=" py-4">
                            <input type="submit" value="Send">
                        </div>
                    </form>
                </div>
            </div>
            <div class="flex flex-col items-end justify-end">
                <iframe class="hidden sm:inline" src="https://giphy.com/embed/LukAHGCMfxMbK" frameBorder="0" allowFullScreen></iframe>
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
    input[type="submit"]{
        border:2px solid var(--primary);
        padding:0px 30px;
    }
    input[type="submit"]:hover{
        color:white;
        padding:2px 37px;
        background:var(--primary);
        transition:.7s;
        border-radius:10px;
    }
    .dateInput{
        border:2px solid var(--primary);
        padding:0 5px;
    }
    @media screen and (min-width:500px){
        .image{
            padding:25px;
        }
    }
</style>

<script>
import imageBitcoin from '../../assets/img/bitcoinImage.png';
    export default {
        name:"MainCard",
        data(){
            return{
                image:imageBitcoin,
                dataBitcoin:{
                    currentPrice:'',
                    date:'',
                }
            }
        },
        props:{
            dataCoin:Object
        },
        mounted(){
            this.insertDataState()
        },
        methods:{
            submitHandler(event){
                event.preventDefault();
            },
            insertDataState(){

                const objectBitcoin = {
                    currentPrice:this.dataCoin,
                    date:this.dataCoin
                }
                this.dataBitcoin = objectBitcoin
            }
        }
    }
</script>