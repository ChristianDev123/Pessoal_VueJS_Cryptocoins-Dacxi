<template>
    <div class="
        grid
        grid-cols-1
        sm:grid-cols-2
        boxSecCard"
    >
        <div class="flex flex-col justify-center text-center px-2">
            <h3>{{dataCoin.nameCoin}}</h3>
        </div>
        <div class="text-center">
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
    .boxSecCard{
        border:1px solid black;
        padding:10px;
    }
    h3, h4{
        color:var(--primary);
    }
    @media screen and (max-width:1024px) {
        h4,h3,p{
            font-size:12px;
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