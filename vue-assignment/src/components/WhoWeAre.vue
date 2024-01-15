<template>
    <div class="who-we-are"> 
    <p class="section-title">{{ articlesData.title }}</p>
    <div class="articles">
        <div v-for="article in articlesData.articles" v-bind:key="article.id" class="article">
          <div class="article-image-container ">
            <img v-bind:src="article.thumbnailUrl" alt="image-not-found" class="article-image"/>
          </div>
          <div class="article-text-div"> 
            <p class="article-title">{{ article.title }}</p>
            <div class="article-excerpt">{{ article.excerpt }}</div>

           <button class="article-show-more-button">SHOW MORE</button> 
          </div>
           
        </div>
    </div>
    
    </div>

</template>

<script>
import axios from 'axios';

export default {
    data() {
    return {
      articlesData: {},
    };
  },
  mounted() { 
    this.fetchArticles();
  },
  methods: {
    fetchArticles() {
      axios.get('https://www.jsonkeeper.com/b/I02R')
        .then(response => {
          console.log(response.data);
          this.articlesData = response.data;
          this.articlesData.title = this.convertToUpperCase(this.articlesData.title); //uppercase nakon primanja podataka
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
    .who-we-are{
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .article-text-div{
      display: flex;
      flex-direction: column;
    }
    .section-title{
        font-size: 2.7rem;
        margin-top: 2rem;
        margin-bottom: 1rem;
    }
    .articles{
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      gap: 2rem;
    }
    
    .article{
      display: flex;
      flex-direction: column;
      align-content: flex-end;
    }
    
    .article-image-container{
      width: 17rem;
      height: 10.2rem;
      overflow: hidden;
    }
    .article-image{
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
    .article-title{
      margin: .8rem 0;
      font-size: 1.5rem;
    }
    .article-excerpt{
      display: none;
    }
    .article-show-more-button{
      background-color: #F3F3F4;
      font-size: .85rem;
      width: 7.3rem;
      height: 2.5rem;
      border-radius: .4rem;
      border: none;
      align-self: flex-end;
      color: #808080;
      font-weight: bold;
      cursor: pointer;
    }
    .article-show-more-button:hover, .article-show-more-button:active, .article-show-more-button:focus, .article-show-more-button:visited{
      background-color: #BBD547;
      color: #FFFFFF;
    }

    @media screen and (min-width: 480px){
      .section-title{
        margin-top: 0;
      }
      .articles{
        width: 42rem;
        gap: 4rem;
        align-items: normal;
      }
      .article{
        flex-direction: row;
        column-gap: 4rem;
      }
      .article-image-container{
        width: 18.8rem;
        height: 11.3rem;
      }
      .article-title{
        margin: 0px;
      }
      .article-text-div{
        width: 18.8rem;
      }
      .article-show-more-button{
        margin-top: auto;
        margin-left: auto;
      }
      .article-title{
        font-size: 1.4rem;
        margin-bottom: 1rem;
      }
      .article-excerpt{
        display: block;
        font-size: 1.3rem;
      }
    }
</style>