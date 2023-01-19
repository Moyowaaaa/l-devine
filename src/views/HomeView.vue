<template>

    <div class="home" v-if="isLoaded">
     
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
import TitleSectionVue from '@/components/TitleSection.vue';
import ShowcaseSection from '../components/ShowcaseSection.vue'
import SubscribeSection from '../components/SubscribeSection.vue'
import AboutSection from '../components/AboutSection.vue'
import FeaturedSection from '../components/FeaturedSection.vue'
import { ref, onMounted } from 'vue';
import cinzelFont from '../assets/fonts/Cinzel-Bold.otf'
import cormorantFont from '../assets/fonts/Cormorant-Medium.otf'
import titlePic1 from '../assets/images/titlepic1.png'
import titlePic2 from '../assets/images/titlePic2.png'
import titlePic3 from '../assets/images/titlepic3.png'

const isLoaded = ref<boolean>(false)
const assets = ref([
    titlePic1,titlePic2,titlePic3
])



onMounted(() => {
    const promises:any[] = []
    assets.value.forEach(asset => {
        const img = new Image()
        img.src = asset
        promises.push(new Promise((resolve, reject) => {
          img.onload = resolve
          img.onerror = reject
        }))        
    })
    new Promise((resolve,reject) => {
        const font = new FontFace('cinzel',`url(${cinzelFont})`)
        font.load().then(resolve,reject)
        const font2 =  new FontFace('cormorant',`url(${cormorantFont})`)
        font2.load().then(resolve,reject)
    })
    Promise.all(promises).then(() => {
        isLoaded.value = true
    })
})


</script>

<style lang="scss" scoped>
.home{
    display: flex;
    flex-direction: column;
    overflow-x: hidden;
    
}
</style>