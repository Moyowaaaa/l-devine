<!-- <template>
    <div>

        <header>
        <div class="header-row">
            <div class="brand-logo">
                <a href="#">
                    <img src="white-logo.svg" alt="">
                </a>
            </div>
            <button class="menu-toggle" id="menuToggle" @click="openMenu">
                <svg viewBox="0 0 12 10" class="hamburger" height="40px" width="40px">
                    <path d="M10,2 L2,2" class="bar-1"></path>
                    <path d="M2,5 L10,5" class="bar-2"></path>
                    <path d="M10,8 L2,8" class="bar-3"></path>

                </svg>
            </button>
        </div>
    </header>

    <section class="fullpage-menu">
        <div class="fullpage-menu-inner">
            <div class="menu-bg">
                <span></span>
                <span></span>
                <span></span>
            </div>

            <nav>
                <ul class="main-menu">
                    <li><a href="">Home</a></li>
                    <li><a href="">About</a></li>
                    <li><a href="">Work</a></li>
                    <li><a href="">Contact</a></li>
                </ul>
            </nav>

            <div class="header-nav-footer">
                <ul class="social-links">
                    <li><a href="#">Facebook</a></li>
                    <li><a href="#">Instagram</a></li>
                    <li><a href="#">Twitter</a></li>
                    <li>&copy;2021</li>
                </ul>
            </div>

        </div>
    </section>

    <section class="placeholder-title">
        <h1>Fullpage Navigation Menu with <span>GSAP</span></h1>
    </section>

    </div>
</template>

<script setup lang="ts">
import {gsap} from 'gsap'
import { onMounted } from 'vue';

var menuBar = gsap.timeline();

var tl = gsap.timeline({ paused: true});


onMounted(() => {
    // var menuToggle = document.getElementById("menuToggle");


menuBar.to('.bar-1', 0.5,{
	attr:{d: "M8,2 L2,8"},
	x:1,
	ease: "power3.inOut"
}, 'start')

menuBar.to('.bar-2', 0.5,{
	autoAlpha: 0
}, 'start')

menuBar.to('.bar-3', 0.5,{
	attr:{d: "M8,8 L2,2"},
	x:1,
	ease: "power3.inOut"
}, 'start')

menuBar.reverse();



tl.to('.fullpage-menu', {
	duration:0,
	display: "block",
	ease: 'Expo.easeInOut',
});

tl.from('.menu-bg span', {
	duration:1,
	x:"100%",
	stagger: 0.1,
	ease: 'Expo.easeInOut'
});

tl.from('.main-menu li a', {
	duration:1.5,
	y:"100%",
	stagger: 0.2,
	ease: 'Expo.easeInOut'
} , "-=0.5");

tl.from('.social-links li', {
	duration:1,
	y:"-100%",
	opacity:0,
	stagger: 0.1,
	ease: 'Expo.easeInOut'
} , "-=0.5");

tl.reverse();

// menuToggle?.addEventListener('click', function(){
// 	menuBar.reversed(!menuBar.reversed());
// 	tl.reversed(!tl.reversed());
// });
})

const openMenu = () => {
    menuBar.reversed(!menuBar.reversed());
	tl.reversed(!tl.reversed());
}

</script>

<style scoped>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    background-color: black;
}


.placeholder-title{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    width: 100%;
    padding-left: 15vw;
    padding-right: 15vw;
}

.placeholder-title h1{
    font-size: 6vw;
    color: #333;
    font-weight: 500;
    text-align: center;
}

/* Header start */

header{
    position: fixed;
    z-index: 10;
    left: 0;
    top: 0;
    width: 100%;
}

.header-row{
    padding:40px 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.brand-logo img{
    height: 40px;
}

.menu-toggle{
    background: transparent;
    border: none;
    cursor: pointer;
}

.hamburger path{
    fill: none;
    stroke: #fff;
    stroke-linecap: round;
}

.fullpage-menu{
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    height: 100vh;
    display: none;
}
.fullpage-menu-inner{
    display: flex;
    align-items: center;
    height: 100%;
    padding: 100px 60px;
}
.menu-bg{
    height: 100%;
    width: 100%;
    position: absolute;
    left: 0;
    top: 0;
}
.menu-bg span{
    height: 33.334%;
    width: 100%;
    background: #e50914;
    display: block;
}

nav{
    position: relative;
    z-index: 10;
}

nav ul{
    list-style-type: none;
}
nav li{
    overflow: hidden;
    transition: transform 300ms ease-in-out 0s;
}
nav li + li{
    margin-top: 20px;
}
nav li a{
    font-size: 100px;
    color: #fff;
    text-decoration: none;
    text-transform: uppercase;
    font-weight: 400;
    display: inline-block;
    line-height: 1;
}
nav li:hover{
    transform: translateX(50px);
}
.header-nav-footer{
    position: absolute;
    z-index: 10;
    bottom: 0;
    left: 0;
    width: 100%;
    display: flex;
    justify-content: space-between;
    padding: 40px 60px;
}
.social-links{
    list-style-type: none;
    display: flex;
    align-items: center;
    width: 100%;
}
.social-links li{
    font-size: 18px;
    font-weight: 500;
}
.social-links li + li{
    margin-left: 16px;
}
.social-links li:last-child{
    margin-left: auto;
}
.social-links a{
    color: #ffffff;
    text-decoration: none;
}

@media screen and (max-width:767px) {
    .header-row, .header-nav-footer{
        padding: 30px;
    }
    .fullpage-menu-inner{
        padding: 70px 30px;
    }
    nav li a{
        font-size: 54px;
    }
    .social-links li{
        font-size: 16px;
    }
}
</style> -->