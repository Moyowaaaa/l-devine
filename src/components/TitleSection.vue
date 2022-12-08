<template>
    <div>
        <navbar />
    <div class="title-section">
        
        
        <div class="title-section__body">
            <h1 class="title-bold title" >Beauty in sight</h1>
            <p class="paragraph-extrasmall paragraph">Get the most luxurious flower collection to bring life into your environment.</p>
            <button class="title-section__button paragraph-extrasmall">
                Browse All</button>
        </div>

        <div class="title-section__image">
           
                <img src="../assets/images/titlepic1.png" class="image1" />
        
                <img src="../assets/images/titlepic2.png" class="image2" />
                <img src="../assets/images/titlepic3.png" class="image3" />

              
                
        </div>
    </div>
    </div>  
</template>

<script setup lang="ts">
import navbar from '../components/Navbar.vue'
</script>

<style lang="scss" scoped>
.title-section{
    height: 100vh;
    overflow-x: hidden;
    display: flex;
    background-image: url('../assets/images/titleBottomBackground.png');
        background-position: left bottom;
        background-repeat: no-repeat;



    
    

    &__body{
        width: 50%;
       
        display: flex;;
        flex-direction: column;
        justify-content: center;
        margin-left:5%;
        ;


       

        .paragraph{
            width: 65%;
            padding-bottom: 5%;
           
        }
        // padding-left: 5%;


    }
    &__button{
        height: auto;
        width:max-content;
        padding: 0.8rem 2rem;
        border: 1px solid black;
        outline: none;
        background-color: transparent;
        
    }

    &__image{
        width: 50%;
        display: flex;

     
    }

 


}
</style>