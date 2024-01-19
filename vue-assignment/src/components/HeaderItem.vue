<template>
  <div id="header" class="header-container">
      <div class="main-content-header">
          <img src="../assets/wm-logo.png" class="wm-logo"/>
          <img src="../assets/wmlogo-large.png" class="wm-logo-large"/>
          <div class="menu-medium">
            <i  class="icon-home icon-hover icon-active icon-focus icon-visited"></i> 
            <!-- ikonica ima prazan krov, bag sa IcoMoon fill property-->
            <i  class="icon-about icon-hover icon-active icon-focus icon-visited"></i>
            <i  class="icon-our-work icon-hover icon-active icon-focus icon-visited"></i>
            <i  class="icon-contact icon-hover icon-active icon-focus icon-visited"></i>
          </div>
          <div class="menu-large"> 
            <div class="header-link">HOME</div>
            <div class="header-link">ABOUT US</div>
            <div class="header-link">OUR WORK</div>
            <div class="header-link">CONTACT</div>
          </div>
        <div>
          <i v-on:click="toggleExpandedMenu" class="icon-burger"></i>
          <i v-on:click="toggleSearchBar" class="icon-search"></i>
        </div>
      </div>
      <div v-if="showSearchBar" class="search-bar">
        <input type="text" placeholder="" class="search-bar-input"/>
      </div>
      <div v-if="showExpandedMenu" class="expanded-menu">
        <div class="expanded-menu-div home">HOME</div>
        <div class="expanded-menu-div about-us">ABOUT US</div> 
        <div class="expanded-menu-div our-work">OUR WORK</div>
        <div class="expanded-menu-div contact">CONTACT</div>
      </div>    
    </div>
  <div class="hr-line"></div>
</template>

<script>
export default {
    data(){
    return{
      showSearchBar: false,
      showExpandedMenu: false,
    }
  },
  methods: {
      toggleSearchBar() {
        setTimeout(() => {
          this.showSearchBar = !this.showSearchBar;
          this.showExpandedMenu = false;
        }, 80);
      },
      toggleExpandedMenu() {
        setTimeout(() => {
          this.showExpandedMenu = !this.showExpandedMenu;
          this.showSearchBar = false;
        }, 80);
      },
  }
}
</script>

<style>
    .header-container{
        background-color: white;
        min-height: 4.6rem;
        display: flex;
        flex-direction: column;
      }
    .main-content-header{
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 5.2rem;
    }
    .wm-logo{
        margin: .5rem;
    }
    .wm-logo-large{
        display: none;
    }
    .icon-burger{
        font-size: 1.5rem;
        cursor: pointer;
    }
    .icon-burger:hover::before, .icon-burger:active::before, .icon-burger:focus::before, .icon-burger:visited::before{
      color: #BBD547;
    }
    .icon-search{
        font-size: 1.5rem;
        margin-left: 1.2rem;
        margin-right: 2rem;
        cursor: pointer;
    }
    .icon-search:hover::before, .icon-search:active::before, .icon-search:focus::before, .icon-search:visited::before{
      color: #BBD547;
    }
    .icon-home{
        font-size: 2rem;
        cursor: pointer;
    }
    .icon-hover:hover::before{
      color: #BBD547;
    }
    .icon-active:active::before{
      color: #81B36E;
    }
    .icon-focus:focus::before{
      color: #429099;
    }
    .icon-visited:visited::before{
      color: #1375B8;
    }
    .icon-about{
        font-size: 2rem; 
        cursor: pointer;
    }
    .icon-our-work{
        font-size: 2rem; 
        cursor: pointer;
    }
    .icon-our-work{
        font-size: 2rem; 
        cursor: pointer;
    }
    .icon-contact{
        font-size: 1.7rem; 
        cursor: pointer;
    }
    .menu-medium{
      display: none;
    }
    .menu-large{
      display: none;
    }
    
    .hr-line{
        height: .8rem;
        background: linear-gradient(to right, #BBD546, #1375B8);
    }
    .search-bar{
      display: flex;
      justify-content: center;
    }

    @keyframes stretchSearch {
      0% {
        width: 1%;
        border-radius: 1rem;
      }
      50% {
        border-radius: .9rem;
      }
      100% {
        width: 100%;
      }
    }

    .search-bar-input{
      height: 2.3rem;
      margin: .8rem;
      padding-left: .3rem;
      border: .1rem solid #808080;
      border-radius: .5rem;
      animation: stretchSearch .8s forwards;
    }
    
    .expanded-menu{
      margin-top: .8rem;
    }

    @keyframes expandMenu {
      0% {
        opacity: 0;
        transform: translateY(-100%);
      }
      100% {
        opacity: 1;
      }
    }

    .expanded-menu-div{
      opacity: 0;
      font-size: 1.4rem;
      color: white;
      padding: .15rem .5rem;
    }
    .home{
      background-color: #BBD547;
      border-bottom: .1rem solid white;
      animation: expandMenu .2s forwards;
      animation-delay: .1s;
    }
    .about-us{
      background-color: #81B36E;
      border-bottom: .1rem solid white;
      animation: expandMenu .2s forwards;
      animation-delay: .3s;
    }
    .our-work{
      background-color: #429099;
      border-bottom: .1rem solid white;
      animation: expandMenu .2s forwards;
      animation-delay: .5s;
    }
    .contact{
      background-color: #1375B8;
      animation: expandMenu .2s forwards;
      animation-delay: .7s;
    }

    @media screen and (min-width: 480px){
      .main-content-header{
        margin-left: 1.4rem;
        margin-right: 1.4rem;
      }
      .menu-medium{
        display: flex;
        justify-content: space-around;
        align-items: center;
        flex-grow: 1;
        margin: 0 2.5rem;
      } 
      .icon-burger{
        display: none;
      }
      .icon-search{
        margin-right: .5rem;
      }
    }

@media screen and (min-width: 768px){
      .menu-medium{
        display: none;
      }
      .menu-large{
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 1.6rem;
        flex-grow: 1;
        margin: 0 2.5rem;
      }
      .wm-logo{
        display: none;
      }
      .wm-logo-large{
        display: block;
      }
      .main-content-header{
        height: 7rem;
      }
      .header-link{
        cursor: pointer;
      }
      .header-link:not(:last-child)::after {
            content: "/";
            margin: 0 .6rem; 
            color: inherit; 
      }
      .header-link:hover{
      color: #BBD547;
      }
      .header-link:active{
      color: #81B36E;
      }
      .header-link:focus{
      color: #429099;
      }
      .header-link:visited{
      color: #1375B8;
      }
    }

    
</style>