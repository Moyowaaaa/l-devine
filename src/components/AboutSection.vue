<script setup lang="ts">
import { gsap } from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import { onMounted } from 'vue';
gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
    let aboutTL = gsap.timeline({
        scrollTrigger: {
            trigger:".about-section",
            start: 'top center',
            end:'top +=30',
          
            scrub:0.1
        }
    })

    aboutTL.fromTo(
    ".about-section_herosection",
    { opacity: 0,scaleX:0.8 },
    {
      y: 0,
      opacity: 1,
      duration: 1.5,
    //   clipPath: "polygon(0 100%, 100% 100%, 100% 0, 0 0)",
    scaleX: 1, 
    z: -500
    },
    "<0.1"
  );
})


</script>


<template>
    <div class="about-section" id="about">
        <div class="about-section__top-section">
            <div class="about-section__top-section__left">
        <img src="../assets/images/afterTitle1.png" />
        </div>
        <div class="about-section__top-section__right">
            <div class="about-section_herosection">
           <p class="paragraph-small">
            “My life is part humor, part roses, part thorns.” – Bret Michael
           </p>     
            </div>
        </div>
        </div> 



        <div class="aboutUsSection">
            <div class="aboutUsSection__maincontainer">
                <div class="aboutUsSection__container">
                <h1 class="title-2-regular title">About Us</h1>


                <div class="aboutUsSection__text-container">
                    <p class="paragraph-regular">
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc, orci curabitur nullam aenean. Amet convallis sit rhoncus, donec. Urna mauris amet ipsum sit laoreet. Semper sed adipiscing nec vivamus nec sed viverra pharetra.
Amet natoque molestie sed semper. Elementum phasellus purus, phasellus augue risus amet duis. Blandit arcu nisi lectus tempor, et hendrerit velit, nisl, dignissim. Viverra blandit in dui non adipiscing malesuada. Leo, eget molestie interdum in suscipit nunc sapien tempor mattis. 
                    </p>

                    </div>

            </div>
            </div>
           
           



        </div>
        
        
        
    </div>
</template>

<style lang="scss" scoped>
.about-section{
    height: auto;
    width: 100%;
    
    &__top-section{
        display: flex;
        @media screen and (max-width:485px) {
    flex-direction: column;
    width: 100%;
}
    }
    &__top-section__left{
        width: 50%;
        display: flex;
        background-color: #8D7362;
        justify-content: center;

        @media screen and (max-width:485px) {
    flex-direction: column;
    width: 100%;
}

    }
    &__top-section__right{
        width: 50%;
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        justify-content: flex-end;
        padding-bottom: 2rem;
        background-image: url('../assets/images/afterTitle2.png');
        background-size: cover;

        @media screen and (max-width:485px) {
    flex-direction: column;
    width: 100%;
    height:40rem
}
    }

}


.about-section_herosection{
    padding: 0.6rem;
    background-color: #ffffff;
    width: 30rem;

    p{
        text-align: right;
        
    }

    @media screen and (max-width:485px) {
 
            display: none;
        
           
    }
}

.aboutUsSection {
display: flex;
justify-content: end;
height: auto;
padding: 2rem 0;
background-image: url('../assets/images/aboutSectionBackground.png');
background-repeat: no-repeat;
background-size: cover;

@media screen and (max-width:485px) {
    flex-direction: column;
    justify-content: start;
    width: 100%;
}


&__maincontainer{
    width: 50%;

    display: flex;
    flex-direction: column;
    align-items: center;

}
&__container{
    display: flex;
    flex-direction: column;
    width: 35rem;

    color: #ffffff;
    text-align: justify;
}

@media screen and (max-width:485px) {

&__container{

    text-align:left;
        width:40rem ;
        padding:0.2rem;
        margin: 0 auto;
    }
}


.title{
    color: white;
    text-align: center;
    
}
@media screen and (max-width:485px) {
    .title{
        text-align: left;
    }
}

}


</style>