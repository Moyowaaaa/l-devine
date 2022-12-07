<template>
    <div class="footer-section">
        <div class="footer-section__credits">
            <span class="footer-text">Designed by <span class="person">Bvlck</span> & <span class="person">Israel </span></span>
            <span class="footer-text">Developed by <span class="person">Moyowa</span></span>
        </div>
        <div class="footer-section__socials">

            <div class="social-links">
  <!-- <img src="../assets/images/facebook.svg" class="social"/> -->
  <img src="../assets/images/instagram.svg" class="social"/>
            <img src="../assets/images/twitter.svg" class="social"/>
            <img src="../assets/images/mail.svg" class="social" />
            </div>

            <div class="copyright">
<img src="../assets/images/copyright.svg" />
<div class="footer-text-small">2022. All right reserved</div>
            </div>
          
        </div>
        <div class="footer-section__navigator">
            <span class="footer-text person">Back to the top</span>
        </div>
    </div>
</template>

<script setup lang="ts">

</script>

<style lang="scss" scoped>
.footer-section {
    height: 50vh;
    overflow-x: hidden;
    display: flex;
    justify-content: space-evenly;


    &__credits{
       width: 33%;
       display: flex;
       flex-direction: column;
       justify-content: center;
       margin-left: 5rem;
       
    }
    &__socials{
       width: 33%;
       display: flex;
       flex-direction: column;
       justify-content: end;
       margin-bottom: 3rem;
       gap:2%;
      

       .social-links{
        display: flex;
        justify-content: center;
        gap: 2%;
        
        
       }

       .social{
        width: 25px;
        padding-bottom: 2%;
       }

       .copyright{
        display:flex;
        justify-content: center;
        gap:1%;
       }
    }
    &__navigator{
       width: 33%;
       display: flex;
       flex-direction: column;
       justify-content: center;
       align-items: flex-end;
       margin-right: 10rem;
    }


    .person{
        text-decoration: underline;
    }


}
</style>