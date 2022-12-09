<template>

    <div class="home">
        <!-- <Menu/> -->
        <PreloaderVue />
        <TitleSectionVue />
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

</script>

<style lang="scss" scoped>
.home{
    display: flex;
    flex-direction: column;
    overflow-x: hidden;
}
</style>