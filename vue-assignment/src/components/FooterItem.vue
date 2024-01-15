<template>
  <div id="footer" class="footer-container">
      <div class="left-side-icons">
        <div class="socials-icon-circle facebook" >
          <i class="icon-facebook"></i>
        </div>
        <div class="socials-icon-circle">
          <i class="icon-twitter"></i>
        </div>
        <div class="socials-icon-circle">
          <i class="icon-email"></i>
        </div>
      </div>
      <div class="footer-text"> 
        <div class="footer-link">HOME</div>
        <div class="footer-link">ABOUT US</div>
        <div class="footer-link">OUR WORK</div>
        <div class="footer-link">CONTACT</div>
      </div>
      <div class="fix"> 
        <div v-on:click="backToTop" class="socials-icon-circle top">
          <i class="icon-top"></i>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  methods: {
    backToTop(){
      document.documentElement.scrollTop = 0;
    }
  }
}
</script>

<style>
    .footer-container{
        height: 5.9rem;
        background-color: #DBDBDB;
        margin-top: 5rem;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .left-side-icons{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .footer-text{
      display: none;
    }
    .icon-top{
      font-size: 2.3rem;
    }
    .icon-top:hover::before, .icon-top:active::before, .icon-top:focus::before, .icon-top:visited::before{
      color: #BBD547;
    }
    .icon-facebook{
      font-size: 2.2rem;
    }
    .icon-facebook:hover::before, .icon-facebook:active::before, .icon-facebook:focus::before, .icon-facebook:visited::before{
      color: #BBD547;
    }
    .icon-twitter{
      font-size: 1.6rem;
    }
    .icon-twitter:hover::before, .icon-twitter:active::before, .icon-twitter:focus::before, .icon-twitter:visited::before{
      color: #BBD547;
    }
    .icon-email{
      font-size: 1.6rem;
    }
    .icon-email:hover::before, .icon-email:active::before, .icon-email:focus::before, .icon-email:visited::before{
      color: #BBD547;
    }
    .socials-icon-circle{
        height: 3.8rem;
        width: 3.8rem;
        border-radius: 50%;
        background-color: #F3F3F4;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: .95rem;
        cursor: pointer;
}

@media screen and (min-width: 480px){
  .facebook{
    margin-left: 3.2rem;
  }
  .top{
    margin-right: 3.5rem;
  }
}

@media screen and (min-width: 768px){
  .footer-container{
    margin-top: 8rem;
  }
  .footer-text{
    display: flex;
    font-size: 1.2rem;
    gap: 1.2rem;
    margin: 0 auto;
  }
  .footer-container{
    justify-content: center;
  }
  .left-side-icons{
    width: 25%;
    justify-content: flex-start;
  }
  .fix{
    width: 25%;
  }
  .top{
    margin-left: auto;
  }
  .footer-link:hover, .footer-link:active, .footer-link:focus, .footer-link:visited{
    color: #BBD547;
  }
}
</style>