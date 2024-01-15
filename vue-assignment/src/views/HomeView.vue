<template>
  <HeaderItem></HeaderItem>
  <ImageSlide></ImageSlide>
  <WhoWeAre></WhoWeAre>
  <WhatWeDo></WhatWeDo>
  <FooterItem></FooterItem>
</template>

<script>
import HeaderItem from '@/components/HeaderItem.vue';
import ImageSlide from '@/components/ImageSlide.vue';
import FooterItem from '@/components/FooterItem.vue';
import WhoWeAre from '@/components/WhoWeAre.vue';
import WhatWeDo from '@/components/WhatWeDo.vue';

export default {
  name: 'HomeView',
  components: {
    HeaderItem,
    ImageSlide,
    FooterItem,
    WhoWeAre,
    WhatWeDo,
  }
}
</script>

<style>
  
</style>
