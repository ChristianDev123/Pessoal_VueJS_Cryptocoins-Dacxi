<template>
    <div class="flex items-center justify-center line py-3 sm:py-0">
        <div class="flex flex-col justify-center items-center line">
            <div class="nameSection py-2">
                <h2>{{dataSection.nameSection}}</h2>
            </div>
            <div class="list">
                <ul class='flex gap-2 sm:gap-0 sm:flex-col'>
                    <li v-for="contact,ids in dataSection.listing" :key="ids" >
                        <a v-if="contact.link != 'none'" :href="contact.link">
                            <div class="flex gap-5">
                                <img :src="contact.image" :alt="contact.platform"/>
                                <p class='hidden sm:inline'>{{contact.text}}</p>
                            </div>
                        </a>
                        <div v-else class="flex gap-5">
                            <img :src="contact.image" :alt="contact.platform"/>
                            <p class='hidden sm:inline'>{{contact.text}}</p>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
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
export default {
    name:'ListingFooter',
    props:["dataSection"]
}
</script>