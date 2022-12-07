<template>
    <div class="showcaseSection">
        <div class="showcaseSection__box1">
            <img src="../assets/images/featuredPic4.svg" class="image"/>
            <img src="../assets/images/featuredPic5.svg" class="image"/>
        </div>

        <!-- <div class="showcaseSection__box2">
            <div class="top-section">
                <img src="../assets/images/featuredPic5.svg" class="image"/>
            <img src="../assets/images/featuredPic6.svg" class="image"/>

            </div>
            <img src="../assets/images/featuredPic7.svg" class="image"/>
            
        </div> -->
    </div>
</template>

<script setup lang="ts">

</script>

<style lang="scss" scoped>
.showcaseSection {
    width: 100vw;
   
    height: 100vh;
    display: flex;
    object-fit:contain;

    &__box1 {
        display: flex;
        flex-direction: column;
        height: 100%;
        width: 40%;
      
    }

    &__box2{
        display: flex;
        flex-direction: column;
        height: 100%;
        width: 60%;
        .top-section{
            display: flex;
        }
        
    }
}
</style>