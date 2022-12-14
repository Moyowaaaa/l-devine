<script setup lang="ts">
import { gsap } from 'gsap';
import { ref, onMounted, watch, watchEffect } from 'vue';
import { useRoute } from 'vue-router';

const navRef = ref(null)
const navTitleRef = ref(null)
const navButtonRef = ref(null)

const closebtnRef = ref()





let showMenu = ref(false)
let navbarIsOpen = ref(false)




const navTl = gsap.timeline()

let navbarTL = gsap.timeline({ paused: true });






onMounted(() => {
  
console.log(showMenu.value)


    navTl.from(navRef.value, {
        opacity:0,
        delay:3.7,
        y:400,
        ease:"power3.inOut"
    })
    navTl.from(navButtonRef.value, {
        x:200,
        duration:1.1,
        ease:"power3.inOut",
        opacity:0
    })

})



const navMenu = () => {
    showMenu.value = !showMenu.value
    console.log('show',showMenu.value)
    if(showMenu.value === true) {
        console.log('yes')
        navbarTL.play()
    }else {
        console.log('no')
    }
    // navbarIsOpen.value = !navbarIsOpen.value
}

// watch(showMenu, () => {
//     if (showMenu.value === true) {
//         navbarTL.play()
//         console.log(navbarTL)
//     }
  
// })
// watch(useRoute(),() => {
//     if(showMenu.value) {
//         showMenu.value = false;
//         navbarTL.reverse()
//     }
// })



</script>

<template>
    <div>
        <div class="navbar" ref="navRef">
        <div class="nav-title" ref="navTitleRef">L'devine</div>
        <div class="nav-button" ref="navButtonRef" @click="navMenu"><img src="../assets/images/kebab.svg"></div>
        </div>


        <!-- --- -->
        <div class="menu" v-if="showMenu">
      
        <div class="menu__image"></div>

        <div class="menu__container">
            <div class="close-btn" @click="navMenu" ref="closebtnRef">
                <img src="../assets/images/close.svg" />
            </div>
      

            <div class="link-container">
                <div>
                <h1 class="menu-title" >HOME</h1>
                <p class="menu-paragraph">Let’s get back to the beginning</p>
                </div>

                <div>
                <h1 class="menu-title" >ABOUT</h1>
                <p class="menu-paragraph">Get to know more about us</p>
                </div>


                <div>
                <h1 class="menu-title">CONTACT US</h1>
                <p class="menu-paragraph">Get in touch we’re never too far</p>
                </div>

                <div>
                <h1 class="menu-title">ORDER</h1>
                <p class="menu-paragraph">Already want the flowers??...nice!!</p>
                </div>


            </div>
        </div>
    </div>
    </div>
</template>



<style lang="scss" scoped>
.navbar{
    overflow-x: hidden;
    width:90%;
    z-index: 12;
    left: 5%;
    // position: fixed;
    position: absolute;
    top:2rem;
    
  
    display: flex;
    background-color: transparent;
    align-items: center;
   
   
    justify-content: space-between;
  
    

}
.nav-title, .nav-button{
    cursor: pointer;
}
.menu{
    height: 100vh;
    width:100%;
    position:fixed;
    background-color: white;
    z-index: 20;

    display: flex;

    &__image{
        width: 50%;
        background-image: url('../assets/images/menuImage.svg');
        background-size: cover;
        background-repeat: no-repeat;
    }

    &__container{
        width: 50%;
        height: 100%;
        display: flex;
        flex-direction: column;
    }

    
}
.close-btn{
    right: 5%;
    position: absolute;
    top:2rem;
    // position: absolute;
    width: 45%;;
    display: flex;
    justify-content: end;

   
}
.link-container{
    padding-top: 8rem;
    padding-left: 10rem;
    cursor:pointer
}

</style>