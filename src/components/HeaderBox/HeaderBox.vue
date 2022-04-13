<template>
    <section >
        <div class="
        flex
        flex-col
        justify-end
        sm:flex-row
        gap-4
        px-24
        py-4
        
        ">
            <a href="" >
                <ButtonHeader>
                    LinkedIn Dev
                </ButtonHeader>
            </a>
            <a href="">
                <ButtonHeader>
                    GitHub Rep.
                </ButtonHeader>
            </a>
            <a href="">
                <ButtonHeader>
                    Vercel Deploy
                </ButtonHeader>
            </a>
        </div>
    </section>
</template>
<script>
import ButtonHeader from '../buttonHeader/buttonHeader.vue' 
    export default {
        name:"Header",
        components:{
            ButtonHeader
        }
    }
</script>