<template>

    <div class="home">
        <!-- <Menu :show="showMenu" @showMenu="openMenu" @closeMenu="closeMenu" :isOpen="navbarIsOpen" /> -->
        <PreloaderVue />
        <TitleSectionVue @showMenu="openMenu" />
    <AboutSection />
    <FeaturedSection />
      <ShowcaseSection/>
    <SubscribeSection />
       
    </div>
    
  
</template>

<script setup lang="ts">
import PreloaderVue from '@/components/Preloader.vue';
import Menu from '../components/Menu.vue'
import TitleSectionVue from '@/components/TitleSection.vue';
import ShowcaseSection from '../components/ShowcaseSection.vue'
import SubscribeSection from '../components/SubscribeSection.vue'
import AboutSection from '../components/AboutSection.vue'
import FeaturedSection from '../components/FeaturedSection.vue'
import { ref } from 'vue';

let showMenu = ref<boolean | any>(false)
let navbarIsOpen = ref<boolean | any>(false)

const openMenu = () => {
    showMenu.value = true
    console.log('show', showMenu.value)
    // navbarIsOpen.value = !navbarIsOpen.value
}

const closeMenu = () => {
    showMenu.value = false
    console.log('show', showMenu.value)
}





// const start = () => {
//     navbarIsOpen.value = !navbarIsOpen.value
//     console.log(navbarIsOpen.value)
// }




</script>

<style lang="scss" scoped>
.home{
    display: flex;
    flex-direction: column;
    overflow-x: hidden;
}
</style>