<script setup lang="ts">
import { gsap } from 'gsap';
import { ref, onMounted } from 'vue';

const navRef = ref<HTMLDivElement | null>(null)
const navTitleRef = ref<HTMLDivElement | null>(null)
const navButtonRef = ref<HTMLDivElement | null>(null)
import MenuVue from './Menu.vue';

let navbarIsOpen = ref<boolean>(false)

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

interface Props{
    showMenu: boolean | any
}
let menuProps = defineProps<Props>()

console.log(menuProps.showMenu)

const toggleNavbar = () => {
    navbarIsOpen.value = !navbarIsOpen.value;
   


    console.log(navbarIsOpen.value)
    // console.log(navbarIsOpen.value)
};

</script>

<template>
    <div class="navbar" ref="navRef">
        <div class="nav-title" ref="navTitleRef">L'devine</div>
        <div class="nav-button" ref="navButtonRef" @click="toggleNavbar"><img src="../assets/images/kebab.svg"></div>

        
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
</style>