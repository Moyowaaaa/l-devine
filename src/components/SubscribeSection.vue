<script setup lang="ts">
import {gsap} from 'gsap'
import {ScrollTrigger} from 'gsap/ScrollTrigger'
import { onMounted, ref } from 'vue';
      gsap.registerPlugin(ScrollTrigger)


      const heroRef = ref(null)

    
</script>

<template>
    <div class="subscribe-section">
        <div class="subscribe-section__left">
            <!-- <img src="../assets/images/newsletterbackgroud.png"/> -->
            <div class="subscribe-section__left__image">
                <!-- <img src="../assets/images/newsletterbackgroud.png" /> -->
            </div>
            <div class="subscribe-section__left__hero" ref="heroRef">
                <p class="paragraph-normal paragraph">
                    “Don't be ashamed to weep; 'tis right to grieve. Tears are only water, and flowers, trees, and fruit cannot grow without water. But there must be sunlight also. A wounded heart will heal in time, and when it does, the memory and love of our lost ones is sealed inside to comfort us.”
                    <br/>
― Brian Jacques, Taggerung
                </p>
          
</div>  
        </div>

        <div class="subscribe-section__right">
            <div class="subscribe-section__right__content">
                <div>
                <h1 class="title-2-regular">Join Our Newsletter</h1>
                <p class="paragraph-extrasmall text">Get updates on our latest flower collection and keep up to date with our latest news.</p>

                <div class="subscribe-section__right__content__formcontainer">
                    <input type="text" class="subscribe-section__right__content__form" placeholder="jondoe@example.com"/>
                    <div class="subscribe-section__right__content__form__text">
                        <p class="paragraph-text">
                        Join
                        </p>
                    </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>



<style lang="scss" scoped>

$black:#131313;
$white:white;
.subscribe-section{
    height: 100vh;
    display: flex;
    width: 100%;
    background-color: black;
    
    color: $white;

    @media screen and (max-width:485px) {
        height: auto;
        flex-direction: column;;
    }

    &__left{
        width: 50%;;
       
       background-image: url('../assets/images/newsletterbackgroud.png');
       background-size: 80% 80%;
       background-position-x: center;
       background-repeat: no-repeat;
       display: flex;
       flex-direction: column;
       justify-content: end;


       @media screen and (max-width:485px) {
       width: 100%;
       background-size: 100% 100%;
    }
    }
  

    &__left__hero{
 
        padding: 2rem;
        display: flex;
        justify-content: center;

        @media screen and (max-width:485px) {
            padding: 1rem;
            text-align: justify;
        }
    }

    &__right{
        width: 50%;;
     
        background-color: #131313;
        display: flex;
        flex-direction: column;
        justify-content: center;
              
       background-image: url('../assets/images/newletterbottom.svg');
       background-position: right bottom;
       background-position-y: 21rem;
       background-repeat: no-repeat;

       @media screen and (max-width:485px) {
        width: 100%;
       }

       
    }

    &__right__content{
        display: flex;
        padding-left: 5rem;

        @media screen and (max-width:485px) {
            padding-left: 1rem;
            padding-bottom: 5rem;
        }
    }

    &__right__content__formcontainer{
        display: flex;


        @media screen and (max-width:485px) {
           flex-direction: column;
           gap:1rem
        }

    }



    &__right__content__form{
        width: 23rem;
       padding: 0.8rem 0.6rem;
       background-color: transparent;
       color: white;
       outline: none;
       border: 1px solid #FFFFFF;

       @media screen and (max-width:485px) {
            width: 90%;
        }
    }
    &__right__content__form::placeholder{
        padding-left: 1.3rem;
        color: #8E8E8E;
    }
    &__right__content__form__text{
        background-color: white;
        padding: 0.8rem 2rem;
        color: black;

        @media screen and (max-width:485px) {
            padding: 0.2rem 2rem; 
            width:10rem;
            margin:0 auto;
            text-align: center;
        }
    }
}
.paragraph-text{
    line-height: 0;
}
.paragraph{
    width: 40rem;
}

.text{
    width: 27rem;

    @media screen and (max-width:485px) {
         width: 90%;
        }
}

</style>