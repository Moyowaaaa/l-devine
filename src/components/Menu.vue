<script setup lang="ts">
import { ref, onMounted } from 'vue';
import {gsap} from 'gsap'

interface menuProps {
    show:boolean,
}
interface menuEmits{
    (e:'showMenu', value:boolean):void
}

defineEmits<menuEmits>()
defineProps<menuProps>()





onMounted(() => {
    const menuTl = gsap.timeline()


    menuTl.from('.close-btn', {scale:1.5, duration:0.7, delay:3.5, })
})
</script>


<template>
    <div class="menu" v-if="show">
        <div class="menu__image"></div>

        <div class="menu__container">
            <div class="close-btn" @click="$emit('showMenu')">
                
                <img src="../assets/images/close.svg" />
            </div>
            <div class="link-container">
                <div>
                <h1 class="menu-title">HOME</h1>
                <p class="menu-paragraph">Let’s get back to the beginning</p>
                </div>

                <div>
                <h1 class="menu-title">ABOUT</h1>
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
</template>



<style lang="scss" scoped>
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
    position: absolute;
    right: 2rem;
    padding:2rem;
    cursor:pointer
}
.link-container{
    padding-top: 8rem;
    padding-left: 10rem;
    cursor:pointer
}
</style>