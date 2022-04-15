<template>
    <div class="grid grid-cols-1 sm:grid-cols-2 border border-black py-2 lg:px-2 rounded-sm containerCard">
        <div class="flex items-center justify-center text-center font-bold">
            <h3>{{dataCoin.nameCoin}}</h3>
        </div>
        <div class='text-center'>
            <div>
                <h4>Current Price (USD):</h4>
                <p>{{dataCoin.currentPrice}}</p>
            </div>
            <div>
                <h4>Date Price:</h4>
                <p>{{dataCoin.datePrice}}</p>
            </div>
        </div>
    </div>    
</template>
<style scoped>
    h3, h4{
        color:var(--primary);
    }
    h3{
        font-size:14px;
        font-weight: bold;
    }
    h4,p{
        font-size:12px;
    }
    .containerCard{
        box-shadow:4px 4px 8px rgba(0, 0, 0, 0.442);
    }
    @media screen and (min-width:900px) {
        h4,p{
            font-size:15px;
        }   
    }
    @media screen and (min-width:1024px) {
        h4,p{
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