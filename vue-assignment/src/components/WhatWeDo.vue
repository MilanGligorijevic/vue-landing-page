<template>
  <div class="what-we-do"> 
    <p class="section-title title-wwd"> {{ itemsData.title }}</p>
    <div class="items">
        <div v-for="item in itemsData.items" :key="item.id" v-bind:class="`item ${item.icon}`">
            <i v-bind:class="`icon-${item.icon}`"></i>
        </div>
    </div>
  </div>
    
</template>

<script>
import axios from 'axios';

export default {
    data() {
    return {
      itemsData: {},
    };
  },
  mounted() {
    this.fetchItems();
  },
  methods: {
    fetchItems() {
      axios.get('https://www.jsonkeeper.com/b/H6I7')
        .then(response => {
          console.log(response.data);
          this.itemsData = response.data;
          this.itemsData.title = this.convertToUpperCase(this.itemsData.title); //uppercase nakon primanja podataka
        })
        .catch(error => {
          console.error('Error fetching data:', error);
        });
    },
    convertToUpperCase(text) {
      console.log(text);
      return text.toUpperCase();
    }
  },
}
</script>

<style>
    .what-we-do{
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
    .section-title{
      font-size: 2.7rem;
    }
    .items{
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      gap: 2.5rem;
    }
    .item{
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: #E9E9E9;
      height: 10.1rem;
      width: 16.8rem;
      cursor: pointer;
    }
    .icon-calculator{
      font-size: 4.4rem;
    }
    .icon-calculator:hover::before, .icon-calculator:active::before, .icon-calculator:focus::before, .icon-calculator:visited::before{
      color: #BBD547;
    }
    .icon-clock{
      font-size: 3.9rem;
    }
    .icon-clock:hover::before, .icon-clock:active::before, .icon-clock:focus::before, .icon-clock:visited::before{
      color: #BBD547;
    }
    .icon-cloud{
      font-size: 3.4rem;
    }
    .icon-cloud:hover::before, .icon-cloud:active::before, .icon-cloud:focus::before, .icon-cloud:visited::before{
      color: #BBD547;
    }
    .icon-heart{
      font-size: 3.9rem;
    }
    .icon-heart:hover::before, .icon-heart:active::before, .icon-heart:focus::before, .icon-heart:visited::before{
      color: #BBD547;
    }

    @media screen and (min-width: 480px){
      .items{
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
        width: 42rem;
        gap: 4rem;
      }
      .item{
        width: 18.8rem;
        height: 11.3rem;
      }
      .cloud{
        order: 2;
      }
      .clock{
        order: 3;
      }
      .calculator{
        order: 1;
      }
      .heart{
        order: 4;
      }
      .section-title{
        width: 42rem;
        font-size: 3rem;
      }
      .title-wwd{
        margin-top: 4.5rem;
      }
    }
</style>