<template>
    <div class="menu" v-if="showMenu">
        <div class="menu__image"></div>

        <div class="menu__container">
            <div class="close-btn">
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

<script setup lang="ts">
import { ref } from 'vue';
const showMenu = ref<boolean>(false)
</script>

<style lang="scss" scoped>
.menu{
    height: 100vh;
    width:100%;
    position:absolute;
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
    padding:2rem
}
.link-container{
    padding-top: 8rem;
    padding-left: 10rem;
}
</style>