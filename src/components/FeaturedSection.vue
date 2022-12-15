<script setup lang="ts">
import {gsap} from 'gsap'
import {ScrollTrigger} from 'gsap/ScrollTrigger'
import { onMounted,ref } from 'vue';
      gsap.registerPlugin(ScrollTrigger)


      const featuredSection = ref<HTMLDivElement | null>(null)
      const featuredHeadText = ref<HTMLTitleElement | null>(null)


    //   onMounted(() => {
    //     let featuredTl = gsap.timeline({
    //         scrollTrigger:{
    //             trigger: featuredSection.value,
    //             start: "top center", // when the top of the trigger hits the top of the viewport
    //   end: "+=50",
    //             markers:true,
    //             scrub:true
    //         }
    //     })

    //     featuredTl.from(featuredSection.value, {
    //         opacity:0,
    //         y:400,
    //         ease:"powert3.inOut"
    //     })
    //     featuredTl.fromTo(featuredHeadText.value,{y: 0, opacity: 0, }, { opacity:1, clipPath: "polygon(0 100%, 100% 100%, 100% 0, 0 0)", delay:0.8}, "<0.3");;
        // featuredTl.from(featuredSection.value, { opacity:0,
        // delay:1.2,
        // y:400,
        // ease:"power3.inOut" })

    //     let featuredSectionTl = gsap.timeline({
    //         scrollTrigger:{
    //             trigger: '.featured-section',
    //             // scrub:0.2
   

    //         }
    //     })

    //     featuredSectionTl.from('.featured-section', {
    //         y:400,
    //         duration:0.8,
    //         opacity:0,
    //         ease:"power3.inOut"
    //     }, "<0.1")

    //   })

</script>


<template>
    <div class="featured-section" >
        <div class="featured-section__maincontainer" ref="featuredSection">
            <h1 class="title-bold title" ref="featuredHeadText">Featured</h1>

            <div class="featured-section__container">
                <div class="featured-section__featuredCard">
                    <img src="../assets/images/featuredPic1.svg" />

                    <div class="featuredCard-hero">
                        <p class="paragraph-bold">Wedding collection</p>
                        <p class="paragraph-text">Wedding collection</p>
                    </div>
                </div>  

                <div class="featured-section__featuredCard">
                    <img src="../assets/images/featuredPic2.svg" />

                    <div class="featuredCard-hero">
                        <p class="paragraph-bold">Party collection</p>
                        <p class="paragraph-text">Wedding collection</p>
                    </div>
                </div>  


                <div class="featured-section__featuredCard">
                    <img src="../assets/images/featuredPic3.svg" />

                    <div class="featuredCard-hero">
                        <p class="paragraph-bold">Custom makes</p>
                        <p class="paragraph-text">Wedding collection</p>
                    </div>
                </div>  

                <!-- <div class="featured-section__featuredCard"></div>  


                <div class="featured-section__featuredCard"></div>   -->
            </div>

            <div class="featured-section__pagination">
                <img src="../assets/images/smallelipse.svg" />
                <img src="../assets/images/largeelipse.svg" />
                <img src="../assets/images/smallelipse.svg" />
            </div>
            </div>  
    </div>
</template>



<style lang="scss" scoped>
.featured-section{
    height: 100vh;
    width: 100%;

    background-image: url('../assets/images/featuredBottom.png');
    
    background-position: left bottom;
        background-repeat: no-repeat;
        background-position-y: 5rem;
       


    &__maincontainer{
        padding-top: 1rem;
        display: flex;
        flex-direction: column;
    }

    &__container{
        display: flex;
        width: 100%;
       
        justify-content:space-around;
       
    }

    &__featuredCard {
        display: flex;
        flex-direction: column;
        width: 20rem;
        height: auto;
   
    }

    &__pagination{
        width: 100%;
        
        display: flex;
        gap:2%;
        justify-content: center;
        padding:4rem 0;
    }
    .title{
        text-align: center;
        padding:2rem 0;
    }
}

.featuredCard-hero{
    padding: 1rem;
    display: flex;
    flex-direction: column;
    background-color: #131313;
    color: white;
}
</style>