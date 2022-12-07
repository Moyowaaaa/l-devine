<template>
    <div class="featured-section">
        <div class="featured-section__maincontainer">
            <h1 class="title-bold title">Featured</h1>

            <div class="featured-section__container">
                <div class="featured-section__featuredCard">
                    <img src="../assets/images/featuredPic1.svg" />

                    <div class="featuredCard-hero">
                        <p class="paragraph-bold">Wedding collection</p>
                        <p class="paragraph-text">Wedding collection</p>
                    </div>
                </div>  

                <div class="featured-section__featuredCard">
                    <img src="../assets/images/featuredPic2.svg" />

                    <div class="featuredCard-hero">
                        <p class="paragraph-bold">Party collection</p>
                        <p class="paragraph-text">Wedding collection</p>
                    </div>
                </div>  


                <div class="featured-section__featuredCard">
                    <img src="../assets/images/featuredPic3.svg" />

                    <div class="featuredCard-hero">
                        <p class="paragraph-bold">Custom makes</p>
                        <p class="paragraph-text">Wedding collection</p>
                    </div>
                </div>  

                <!-- <div class="featured-section__featuredCard"></div>  


                <div class="featured-section__featuredCard"></div>   -->
            </div>

            <div class="featured-section__pagination">
                <img src="../assets/images/smallelipse.svg" />
                <img src="../assets/images/largeelipse.svg" />
                <img src="../assets/images/smallelipse.svg" />
            </div>
            </div>  
    </div>
</template>

<script setup lang="ts">

</script>

<style lang="scss" scoped>
.featured-section{
    height: 100vh;
    width: 100%;

    // background-image: url('../assets/images/featuredBottom.png  ');
    //     background-position: left bottom;
    //     background-repeat: no-repeat;
    &__maincontainer{
        padding-top: 1rem;
        display: flex;
        flex-direction: column;
    }

    &__container{
        display: flex;
        width: 100%;
       
        justify-content:space-around;
       
    }

    &__featuredCard {
        display: flex;
        flex-direction: column;
        width: 20rem;
        height: auto;
   
    }

    &__pagination{
        width: 100%;
        
        display: flex;
        gap:2%;
        justify-content: center;
        padding:4rem 0;
    }
    .title{
        text-align: center;
        padding:2rem 0;
    }
}

.featuredCard-hero{
    padding: 1rem;
    display: flex;
    flex-direction: column;
    background-color: #131313;
    color: white;
}
</style>