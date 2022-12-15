<template>
    <div class="showcaseSection">
        <div class="showcaseSection__row">
            <div class="showcaseSection__column">
                <div class="showcaseSection__column__top"></div>
                <div class="showcaseSection__column__bottom"></div>
                <!-- <img src="../assets/images/featuredPic4.svg" />
                <img src="../assets/images/featuredPic8.svg" /> -->
            </div>
            <div class="showcaseSection__column2">
                <!-- <img src="../assets/images/featuredPic5.svg" /> -->
                <div class="showcaseSection__topRow">
                    <div class="showcaseSection__topRowleft"></div>
                        <div class="showcaseSection__topRowright"></div>
                </div>
                <div class="showcaseSection__bottomRow"></div>
                
            </div>
            
        </div>
    </div>
</template>

<script setup lang="ts">

</script>

<style lang="scss" scoped>
.showcaseSection{
    height:auto;

    &__row{
        height: 100%;
        display:flex;

        
        @media screen and (max-width:485px) {
    flex-direction: column;
    height: auto;
    width: 100%;
}
    }
    &__column {
       
        width: 33.3%;
        object-fit: contain;
        display: flex;
        flex-direction: column;
        height:90rem;

        @media screen and (max-width:485px) {
  
    width: 100%;
}
    }
    &__column__top{
        height: 50%;
  
        background-image: url('../assets/images/featuredPic4.svg');
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;

        
    
    }
    &__column__bottom{
        height: 50%;
     
        background-image: url('../assets/images/featuredPic8.svg');
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
    }

    &__column2{
       
        width: 66.6%;
        object-fit: contain;
        display: flex;
        flex-direction: column;

        @media screen and (max-width:485px) {
   
    width: 100%;
}
    }

    &__topRow{
        display: flex;
        height: 60%;
    
    }

    &__topRowleft{
        background-image: url('../assets/images/featuredPic5.svg');
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
        height: 100%;
        width: 50%;
    }
    

    &__topRowright{
        background-image: url('../assets/images/featuredPic6.svg');
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
        height: 100%;
        width: 50%;
    }

    &__bottomRow{
        background-image: url('../assets/images/featuredPic7.svg');
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
        height: 40%;
        width: 100%;
    }
    

}
</style>