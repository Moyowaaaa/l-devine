<script setup lang="ts">
import {gsap} from 'gsap'
import {ScrollTrigger} from 'gsap/ScrollTrigger'
import { onMounted,ref } from 'vue';
      gsap.registerPlugin(ScrollTrigger)


      const featuredSection = ref<HTMLDivElement | null>(null)
      const featuredHeadText = ref<HTMLTitleElement | null>(null)
      const featuredContainer = ref<HTMLDivElement | null>(null)
     


      onMounted(() => {
        let featuredTl = gsap.timeline({
            scrollTrigger:{
                trigger: featuredSection.value,
                start: 'top center',
            end:'top +=10',
         
                scrub:true
            }
        })

        let featuredTL2 = gsap.timeline({
            scrollTrigger:{
                trigger:featuredSection.value,
                start: 'top center',
            end:'top +=10',
            }
        })

        featuredTl.fromTo(featuredHeadText.value,{ opacity: 0, scaleX: 1,  },
    {
      y: 0,
      opacity: 1,
      duration: 1.5,
      clipPath: "polygon(0 100%, 100% 100%, 100% 0, 0 0)",
    // scaleX: 1, 
    z: -500
    });
    featuredTL2.from('.featured-section__container', {
        stagger: .6,
        duration:4,
        y:"200px",
        opacity:0,
        ease:"power3.inOut"
    })

      })

</script>


<template>
    <div class="featured-section" >
        <div class="featured-section__maincontainer" ref="featuredSection">
            <h1 class="title-bold title" ref="featuredHeadText">Featured</h1>

            <div class="featured-section__container" ref="featuredContainer">
                <div class="featured-section__featuredCard">
                    <img src="../assets/images/featuredPic1.svg"  alt=""/>

                    <div class="featuredCard-hero">
                        <p class="paragraph-bold">Wedding collection</p>
                        <p class="paragraph-text">Wedding collection</p>
                    </div>
                </div>  

                <div class="featured-section__featuredCard">
                    <img src="../assets/images/featuredPic2.svg" alt=""/>

                    <div class="featuredCard-hero">
                        <p class="paragraph-bold">Party collection</p>
                        <p class="paragraph-text">Wedding collection</p>
                    </div>
                </div>  


                <div class="featured-section__featuredCard">
                    <img src="../assets/images/featuredPic3.svg" alt=""/>

                    <div class="featuredCard-hero">
                        <p class="paragraph-bold">Custom makes</p>
                        <p class="paragraph-text">Wedding collection</p>
                    </div>
                </div>  

                <!-- <div class="featured-section__featuredCard"></div>  


                <div class="featured-section__featuredCard"></div>   -->
            </div>

            <div class="featured-section__pagination">
                <img src="../assets/images/smallelipse.svg" alt=""/>
                <img src="../assets/images/largeelipse.svg" alt=""/>
                <img src="../assets/images/smallelipse.svg" alt=""/>
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

        @media screen and (max-width:485px) {
  height:auto;
}
       


    &__maincontainer{
        padding-top: 1rem;
        display: flex;
        flex-direction: column;
    }

    &__container{
        display: flex;
        width: 100%;
       
        justify-content:space-around;

        @media screen and (max-width:485px) {
    flex-direction: column;
    width: 100%;
}
       
    }

    &__featuredCard {
        display: flex;
        flex-direction: column;
        width: 20rem;
        height: auto;

        @media screen and (max-width:485px) {
            padding:1rem 0;
            width: 90%;
            margin: 0 auto;
}
   
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