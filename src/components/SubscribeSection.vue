<template>
    <div class="subscribe-section">
        <div class="subscribe-section__left">
            <!-- <img src="../assets/images/newsletterbackgroud.png"/> -->
            <div class="subscribe-section__left__image">
                <!-- <img src="../assets/images/newsletterbackgroud.png" /> -->
            </div>
            <div class="subscribe-section__left__hero">
                <p class="paragraph-normal paragraph">
                    “Don't be ashamed to weep; 'tis right to grieve. Tears are only water, and flowers, trees, and fruit cannot grow without water. But there must be sunlight also. A wounded heart will heal in time, and when it does, the memory and love of our lost ones is sealed inside to comfort us.”
                    <br/>
― Brian Jacques, Taggerung
                </p>
          
</div>  
        </div>

        <div class="subscribe-section__right">
            <div class="subscribe-section__right__content">
                <div>
                <h1 class="title-2-regular">Join Our Newsletter</h1>
                <p class="paragraph-extrasmall text">Get updates on our latest flower collection and keep up to date with our latest news.</p>

                <div class="subscribe-section__right__content__formcontainer">
                    <input type="text" class="subscribe-section__right__content__form" placeholder="jondoe@example.com"/>
                    <div class="subscribe-section__right__content__form__text">
                        <p class="paragraph-text">
                        Join
                        </p>
                    </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">

</script>

<style lang="scss" scoped>

$black:#131313;
$white:white;
.subscribe-section{
    height: 100vh;
    display: flex;
    width: 100%;
    background-color: black;
    
    color: $white;


    &__left{
        width: 50%;;
       
       background-image: url('../assets/images/newsletterbackgroud.png');
       background-size: 80% 80%;
       background-position-x: center;
       background-repeat: no-repeat;
       display: flex;
       flex-direction: column;
       justify-content: end;
    }
  

    &__left__hero{
 
        padding: 2rem;
        display: flex;
        justify-content: center;
    }

    &__right{
        width: 50%;;
     
        background-color: #131313;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    &__right__content{
        display: flex;
        padding-left: 5rem;
    }

    &__right__content__formcontainer{
        display: flex;
    }
    &__right__content__form{
        width: 23rem;
       padding: 0.8rem 0.6rem;
       background-color: transparent;
       color: white;
       outline: none;
       border: 1px solid #FFFFFF;
    }
    &__right__content__form::placeholder{
        padding-left: 1.3rem;
        color: #8E8E8E;
    }
    &__right__content__form__text{
        background-color: white;
        padding: 0.8rem 2rem;
        color: black;
    }
}
.paragraph-text{
    line-height: 0;
}
.paragraph{
    width: 40rem;
}

.text{
    width: 27rem;
}

</style>