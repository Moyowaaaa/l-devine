<script setup lang="ts">
import {gsap} from 'gsap'
import {ScrollTrigger} from 'gsap/ScrollTrigger'
import { onMounted, ref, inject,onUnmounted } from 'vue';
gsap.registerPlugin(ScrollTrigger)
const isLoaded = inject('isLoaded')
const scrollToTop = () =>  {
            window.scrollTo({
                top:0,
                behavior: 'smooth'
            })
        }

      

        let year = ref<any>()
onMounted(()=> {
    const date = new Date();
   year.value = date.getFullYear()
})




</script>


<template>
    <div class="footer-section" id="contact" v-if="isLoaded">
        <div class="footer-section__credits" ref="creditsRef">
            <span class="footer-text">Designed by <a href="https://www.behance.net/adesiyanbss"> <span class="person">Bvlck</span></a> & <a href="https://www.behance.net/israeladeniyi8"><span class="person">Israel </span></a></span>
            <span class="footer-text">Developed by <a href="https://github.com/Moyowaaaa"><span class="person">Moyowa</span></a></span>
        </div>
        <div class="footer-section__socials">

            <div class="social-links" ref="socialLinksRef">
  <!-- <img src="../assets/images/facebook.svg" class="social"/> -->
  <img src="../assets/images/instagram.svg" class="social instagram"  alt="instagram"/>
            <img src="../assets/images/twitter.svg" class="social twitter"  alt="facebook"/>
            <img src="../assets/images/mail.svg" class="social mail"  alt="twitter"/>
            </div>

            <div class="copyright">
<img src="../assets/images/copyright.svg" alt="copyright"/>
<div class="footer-text-small"><span>{{ year }}</span> All right reserved</div>
            </div>
          
        </div>
        <div class="footer-section__navigator">
            <button class="footer-text person" @click="scrollToTop">Back to the top</button>
        </div>
    </div>
</template>



<style lang="scss" scoped>
a{
    color:black;
    text-decoration: none;
}
button{
    outline: none;
    border: none;
    background-color: transparent;
    cursor:pointer
}
.footer-section {
    height: 50vh;
    overflow: hidden;
    display: flex;
    justify-content: space-evenly;

    @media screen and (max-width:485px) {
       flex-direction: column;
       }


    &__credits{
       width: 33%;
       display: flex;
       flex-direction: column;
       justify-content: center;
       margin-left: 5rem;

       @media screen and (max-width:485px) {
        width: 100%;
        margin-left:2rem
       }
       
    }
    &__socials{
       width: 33%;
       display: flex;
       flex-direction: column;
       justify-content: end;
       margin-bottom: 3rem;
       gap:2%;

       @media screen and (max-width:485px) {
        width: 100%;
        // margin-left:
        align-items: center;;

       }
       .social-links{
        display: flex;
        justify-content: center;
        gap: 2%;
        

        @media screen and (max-width:485px) {
        justify-content: start;
        gap:2rem;
        }
        
        
       }

       .social{
        width: 25px;
        padding-bottom: 2%;
       }

       .copyright{
        display:flex;
        justify-content: center;
        gap:1%;


        @media screen and (max-width:485px) {
        justify-content: start;
        display:none
        }
       }

       
    }
    &__navigator{
       width: 33%;
       display: flex;
       flex-direction: column;
       justify-content: center;
       align-items: flex-end;
       margin-right: 10rem;

       @media screen and (max-width:485px) {
        width: 100%;
        margin-right:2rem;
        
       }
    }


    .person{
        text-decoration: underline;
    }


}
</style>