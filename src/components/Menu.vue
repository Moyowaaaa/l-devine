<script setup lang="ts">
import { ref, onMounted, onUnmounted, toRefs, computed,watch } from 'vue';
import {gsap} from 'gsap'

interface menuProps {
    show:boolean,
    isOpen:boolean
}
interface menuEmits{
    (e:'showMenu', value:boolean):void
    (e:'closeMenu', value:boolean):void
}

defineEmits<menuEmits>()
const navProps = defineProps<menuProps>()

const closebtnRef = ref(null)

const {show, isOpen} = toRefs(navProps)

    console.log('menu',show.value)


</script>


<template>
    <div class="menu">
   
        <div class="menu__image"></div>

        <div class="menu__container">
            <div class="close-btn" @click="$emit('closeMenu')" ref="closebtnRef">
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