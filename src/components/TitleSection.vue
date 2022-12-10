<script setup lang="ts">

import navbar from '../components/Navbar.vue'
import {gsap} from 'gsap'
import { onMounted, ref } from 'vue';

const titleText = ref<HTMLDivElement | null>(null)
const titleImage1 = ref<HTMLDivElement | null>(null)
const titleImage2 = ref<HTMLDivElement | null>(null)
const titleImage3 = ref<HTMLDivElement | null>(null)
const titleImageText = ref<HTMLDivElement | null>(null)


interface Props{
    showMenu: boolean | any
}

const titleProps = defineProps<Props>()

console.log('showwwww',titleProps.showMenu)
onMounted(() => {
    const tl =gsap.timeline()
    tl.from('.title-section', {
        opacity:0,
        delay:3.7,
        y:400,
        ease:"power3.inOut"
    })
    tl.fromTo(titleText.value,  {y: 0, opacity: 0, }, { opacity:1,duration:3.2, clipPath: "polygon(0 100%, 100% 100%, 100% 0, 0 0)"}, "<0.1");;
    tl.from(titleImage1.value, {
        x:-400,
        opacity:0,
        duration:1.2,
        ease:"power3.inOut"
    }, "<0.1")
    tl.from(titleImage2.value, {
        x:-400,
        opacity:0,
        duration:1.2,
        ease:"power3.inOut",
        
    }, "<0.1")
    tl.from(titleImage3.value, {
        x:-400,
        opacity:0,
        duration:1,
        ease:"power3.inOut"
    }, "<0.1")
    tl.from(titleImageText.value, {
        y:20,
        opacity:0,
        duration:1.5,
        ease:"power3.inOut"
    }, "<0.1")
})
</script>

<template>
    <div>
        <navbar :showMenu="showMenu"/>
    <div class="title-section">
        
        
        <div class="title-section__body" ref="titleText">
            <h1 class="title-bold title" >Beauty in sight</h1>
            <p class="paragraph-extrasmall paragraph">Get the most luxurious flower collection to bring life into your environment.</p>
            <button class="title-section__button paragraph-extrasmall">
                Browse All</button>
        </div>


        <div class="title-section__image1" ref="titleImage1"> </div>
        <div class="title-section__image2" ref="titleImage2"></div>
<div class="title-section__image3" ref="titleImage3">
    <div class="title-section__sub-container" ref="titleImageText">
        <p class="paragraph-text">“The earth laughs in flowers.”
        </p>
        <p class="paragraph-text">
― Ralph Waldo Emerson</p>
    </div>
</div>
    

</div>
    </div>  
</template>



<style lang="scss" scoped>
.title-section{
    height: 100vh;
    overflow: hidden;
    display: flex;
    background-image: url('../assets/images/titleBottomBackground.png');
        background-position: left bottom;
        background-repeat: no-repeat;



    
    

    &__body{
        width: 50%;
       
        display: flex;;
        flex-direction: column;
        justify-content: center;
        margin-left:5%;
        ;


       

        .paragraph{
            width: 65%;
            padding-bottom: 5%;
           
        }
        // padding-left: 5%;


    }
    &__button{
        height: auto;
        width:max-content;
        padding: 0.8rem 2rem;
        border: 1px solid black;
        outline: none;
        background-color: transparent;
        
    }

    &__image{
        width: 50%;
        display: flex;

     
    }

    &__image1{
    background-image: url('../assets/images/titlePic1.png');
    height: 100%;
    width: 8%;
    background-repeat: no-repeat;
    background-size: cover;


}
&__image2{
    background-image: url('../assets/images/titlePic2.png');
    background-repeat: no-repeat;
    background-size: cover;

    height: 100%;
    width: 7%;
    

}
&__image3{
    background-image: url('../assets/images/titlePic3.png');
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    flex-direction: column;
    height: 100%;
    width: 35%;
    justify-content: end;
    
}

&__sub-container{
    padding: 0 1.2rem;
  
    width:fit-content;
    color:white;
    padding-bottom: 6rem;
    padding-left: 2.2rem;
}




}
.title-text{
    position:absolute;
    right:15rem;
    padding: 1rem;
    border:2px solid red;
  
}

</style>