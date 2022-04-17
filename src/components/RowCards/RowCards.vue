<template>
    <div class="grid grid-cols-1 border border-black py-2 px-2 rounded-sm containerCard">
        <div>
            <h3 class="font-bold">{{dataCoin.nameCoin}} - {{dataCoin.symbolCoin}}</h3>
        </div>
        <div class='text-center'>
            <h2>{{dataCoin.currentPrice}}</h2>
        </div>
        <div class='flex flex-wrap justify-between'>
            <p class="font-bold">{{dataCoin.datePrice}}</p>
            <p class='font-bold'>{{dataCoin.timePrice}}</p>
        </div>
    </div>    
</template>
<style scoped>
    h3, p{
        color:var(--primary);
    }
    p{
        font-size:12px;
    }
    h2{
        font-size:23px;
    }
    h3{
        font-size:14px;
    }
    .containerCard{
        box-shadow:4px 4px 8px rgba(0, 0, 0, 0.442);
    }
    @media screen and (min-width:800px) {
        h3{
            font-size:18px;
        }
        h2{
            font-size:33px;
        }
        p{
            font-size:16px;
        }
    }
    @media screen and (min-width:900px) {
        h3{
            font-size:15px;
        }
        h2{
            font-size:35px;
        }
        p{
            font-size:13px;
        }   
    }
</style>
<script>
    export default {
        name:"RowCards",
        props:{
            dataCoin: Object,
        }
    }
</script>