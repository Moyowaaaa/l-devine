<script setup lang="ts">
import { gsap } from 'gsap';
import { ref, onMounted, watch } from 'vue';

const navRef = ref<HTMLDivElement | null>(null)
const navTitleRef = ref<HTMLDivElement | null>(null)
const navButtonRef = ref<HTMLDivElement | null>(null)

const closebtnRef = ref(null)



onMounted(() => {
    const navTl = gsap.timeline()

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


let showMenu = ref<boolean | any>(false)
let navbarIsOpen = ref<boolean | any>(false)




let nav = ref(showMenu.value)

const NavbarTL = gsap.timeline({ paused: true });

onMounted(() => {
    NavbarTL.from(closebtnRef.value, {
        duration:1.2,
        delay:0.5,
        scale:2.5,
        opacity:0,
        ease:"power3.inOut"
    })
})

const NavMenu = () => {
    showMenu.value = !showMenu.value
    if(showMenu.value === true) {
        NavbarTL.play()
    } else {
        NavbarTL.reverse()
    }
    console.log('show', showMenu.value)
    // navbarIsOpen.value = !navbarIsOpen.value
}


</script>

<template>
    <div>
        <div class="navbar" ref="navRef">
        <div class="nav-title" ref="navTitleRef">L'devine</div>
        <div class="nav-button" ref="navButtonRef" @click="NavMenu"><img src="../assets/images/kebab.svg"></div>
        </div>


        <!-- --- -->
        <div class="menu" v-if="showMenu">
        <div class="menuIsOpen" v-if="showMenu">
            menuuu
        </div>
        <div class="menu__image"></div>

        <div class="menu__container">
            <div class="close-btn" @click="NavMenu" ref="closebtnRef">
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