<script setup lang="ts">
import { gsap } from 'gsap';
import { ref, onMounted, watch, watchEffect } from 'vue';
import { useRoute } from 'vue-router';

const navRef = ref(null)
const navTitleRef = ref(null)
const navButtonRef = ref(null)

const closebtnRef = ref()



const navLinks =[ 
    {title:"HOME", description:"Let’s get back to the beginning"}, 
    {title:"ABOUT", description:"Get to know more about us"},
    {title:"CONTACT US", description:"Get in touch we’re never too far"},
    {title:"ORDER", description:"Already want the flowers??...nice!!"}

]

var menuTl = gsap.timeline()

var menuBodyTl = gsap.timeline({paused:true})

onMounted(() => {
    menuTl.to('.bar-1', {
        duration:0.5,
        attr:{d: "M8,2 L2,8"},
	x:1,
	ease: "power3.inOut"
    }, 'start')

    menuTl.to('.bar-2',{
	autoAlpha: 0,
    duration:0.5
}, 'start')

    menuTl.to('.bar-3',{
	attr:{d: "M8,8 L2,2"},
    duration:0.5,
	x:1,
	ease: "power3.inOut"
}, 'start')

menuTl.to('.nav-button', {
    display:"none",
    delay:0.6,
})

menuTl.reverse()

menuBodyTl.to('.menu', {
    duration:0.2,
	display: "block",
	ease: 'Expo.easeInOut',
 
})



// menuBodyTl.from('.menu__background span', {
// 	duration:1,
// 	x:"100%",
// 	stagger: 0.1,
// 	ease: 'Expo.easeInOut'
// });





menuBodyTl.to('.bar1', {
        duration:0.5,
        attr:{d: "M8,2 L2,8"},
	x:1,
	ease: "power3.inOut"
    }, 'start')

    menuBodyTl.to('.bar2',{
	autoAlpha: 0,
    duration:0.5
}, 'start')

    menuBodyTl.to('.bar3',{
	attr:{d: "M8,8 L2,2"},
    duration:0.5,
	x:1,
	ease: "power3.inOut"
}, 'start')

menuBodyTl.from('.link', {
    opacity:0,
    duration:1.2,
    stagger: 0.2,
    y:200,
    ease:"power3.inOut"
}, "<0.1")

menuBodyTl.from('.menu__image', {
    scale:1.5,
    opacity:0,
    duration:0.6,
    ease:"power3.inOut"
}, "<0.1")



menuBodyTl.reverse()

})

const openMenu = () => {
    menuTl.reversed(!menuTl.reversed())
    menuBodyTl.reversed(!menuBodyTl.reversed())
}







</script>

<template>
    <div>
        <div class="navbar" ref="navRef">
        <div class="nav-title" ref="navTitleRef">L'devine</div>
        <div class="nav-button" ref="navButtonRef" @click="openMenu" 
         id="menuToggle">
            
            <!-- <img src="../assets/images/kebab.svg"> -->
            <svg viewBox="0 0 12 10" class="hamburger" height="40px" width="40px">
                    <path d="M10,2 L2,2" class="bar1"></path>
                    <path d="M2,5 L10,5" class="bar2"></path>
                    <path d="M10,8 L2,8" class="bar3"></path>

                </svg>
        
        </div>
        </div>

    <div class="menu">
        
        <!-- <div class="menu__background">
                <span></span>
                <span></span>
                <span></span>
            </div> -->


            <div class="close-btn" @click="openMenu"  ref="closebtnRef">
      
        <svg viewBox="0 0 12 10" class="hamburger" height="40px" width="40px">
            <path d="M10,2 L2,2" class="bar-1"></path>
            <path d="M2,5 L10,5" class="bar-2"></path>
            <path d="M10,8 L2,8" class="bar-3"></path>

        </svg>
    </div>

    <div class="menu__main-container">
        <div class="menu__image"></div>

        <div class="links-container">
            <div class="link-container">
                <div class="link" v-for="link in navLinks">
                    <h1 class="menu-title" >{{link.title}}</h1>
                <p class="menu-paragraph">{{link.description}}</p>
                </div>

           


            </div>
        </div>
    </div>

       
    </div>
    </div>
</template>



<style lang="scss" scoped>

.nav-button{
    background-color: white;
    padding:5px 10px;
    cursor: pointer;
}


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
    z-index: 100;
  
    display: none;
    overflow: hidden;


    &__background{
        height: 100%;;
        width: 100%;
      z-index: 2;
   


        span{
            height: 33.334%;
    width: 100%;
    background: #e50914;
    display: block;
        }
    }

    &__image{
        width: 50%;
        background-image: url('../assets/images/menuImage.svg');
        background-size: cover;
        background-repeat: no-repeat;
    }




}


.close-btn{
    right: 5%;
    z-index: 70;
    position: absolute;
    top:2rem;
    cursor: pointer;
}


.hamburger path{
    fill: none;
    stroke: black;
    stroke-linecap: round;
}
.menu__main-container{
    width: 100%;;
    height: 100vh;
   
    z-index: 50;
    background-color: white;
    position: fixed;
    display: flex;
}

.links-container{
    width: 50%;
}

.link-container{
    height: 100%;

    padding: 10rem 10rem;
}




</style>