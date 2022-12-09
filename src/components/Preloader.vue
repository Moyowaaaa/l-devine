<script setup lang="ts">
import { ref, onMounted } from "vue";
import { gsap } from "gsap";

const preloaderRef = ref<HTMLDivElement | null>(null);
const barRef = ref<HTMLDivElement | null>(null);

const loadingPercentage = ref<number | any>(0);
let lo = ref<boolean>();

const load = () => {
  const id = setInterval(function () {
    loadingPercentage.value = loadingPercentage.value + 1;
  }, 10);
  setTimeout(() => {
    clearInterval(id);
  }, 1000);
};

onMounted(() => {
  const loaderTl = gsap.timeline();

  loaderTl.from('.preloader', {
        opacity:0,
        delay:0.3,
        duration:0.2,
        ease:"power3.inOut"
    }),
  loaderTl
    .to(".preloader__bar", {
      duration: 1,
      transform: `translate3d(0%, 0, 0)`,
      onStart: load,
    })
    .fromTo(
      ".text",
      { y: 0, opacity: 0 },
      {
        opacity: 1,
        delay:0.1,
        duration: 0.4,
        clipPath: "polygon(0 100%, 100% 100%, 100% 0, 0 0)",
      },
      "<0.1"
    )

    .to(".blackText", {
      delay: 0.6,
      duration: 0.8,
      opacity: 0,
    })
    .fromTo(
      ".reveal",
      { y: 0, opacity: 0 },
      {
        
        opacity: 1,
        duration: 0.8,
        clipPath: "polygon(0 100%, 100% 100%, 100% 0, 0 0)",
      },
      "<0.1"
    )
    .to(
      ".reveal",
      {
        delay: 0.1,
        duration: 1,
        y: -100,
        ease: "power3.inOut",
        opacity: 0,
      },
      "-=0.25"
    );

  loaderTl.eventCallback("onComplete", () => {
    loaderTl.kill();
    gsap.set(".preloader", { zIndex: -1 });
  });
});
</script>

<template>
  <div class="preloader">
    <div class="preloader__container" ref="preloaderRef">
      <div class="preloader__bar" ref="barRef"></div>
      <div class="preloader__textcontainer">
        <p class="text">L'DEVINE</p>
        <!-- <p class="text blackText">L'DEVINE</p> -->
        <p class="percentage">
          <span v-if="loadingPercentage.toString().length === 1 && 0"> </span>
          <span>
            {{ loadingPercentage }}
          </span>
        </p>
      </div>

      <div class="text-reveal-container">
        <div class="text-reveal-container__text reveal">L'DEVINE</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.preloader {
  //    color:;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  &__container {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background: #0b0b0b;
    margin: auto;
    z-index: 40;
  }

  &__bar {
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 100%;
    background: #fff;
    transform: translate3d(-100%, 0, 0);
  }

  &__textcontainer {
    position: fixed;
    bottom: 0;
    right: 0;
    padding: 5%;
    text-align: right;
  }
}

.text {
  font-size: 1.125rem;
  color: #fff;
  font-family: "grotesk-bold";

  &.blackText {
    position: absolute;
    top: 50%;
    color: #000;
    opacity: 0;
    
    transform: translateY(-50%);
    clip: rect(0px, 135px, 45px, 0px);
  }
}

.percentage {
  color: white;
  font-size: 70px;
  font-weight: 700;
  display: flex;
  font-family: "grotesk-bold";
}

.text-reveal-container {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  font-size: 50px;

  &__text {
    font-family: "cormorant";
    font-weight: 700;
    font-size: 70px;
  }
}
</style>
