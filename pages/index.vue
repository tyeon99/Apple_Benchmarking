<template>
  <div class="landing">
    <LandingProduct 
      v-for="(product, idx) in products"
      :key="'product_' + idx"
      :product="product"
      :idx="idx"
    />
    <LandingService />
    <LandingSwiper />
  </div>
</template>

<script>
import LandingProduct from '~/components/landing/LandingProduct.vue'

export default {
  components: {
    LandingProduct
  },
  layout: 'default',
  data: () => ({
    products: [
      { 
        title: 'iPhone 15 Pro', 
        txt: '티타늄.초강력.초경량.초프로.', 
        imgurl: 'https://www.apple.com/v/home/bo/images/heroes/iphone-15-pro/hero_iphone15pro__i70z9oz3hj2i_mediumtall.jpg', 
        simgurl: 'https://www.apple.com/v/home/bo/images/heroes/iphone-15-pro/hero_iphone15pro__i70z9oz3hj2i_small.jpg' 
      },
      { 
        title: 'iPhone 15', 
        txt: '새로운 카메라.새로운 디자인.새로움이 물씬.', 
        imgurl: require('@/assets/img/iphone15_largeImg.png'), 
        simgurl: 'https://www.apple.com/v/home/bo/images/heroes/iphone-15/hero_iphone15_announce__uuemlcwczn6u_small.jpg' 
      },
      { 
        title: 'iPad Pro',
        txt: '놀라우리만치 얇다.엄청나게 강력하다.',
        imgurl: 'https://www.apple.com/v/home/bo/images/heroes/ipad-pro/hero_ipadpro__bpt7a9d8sh42_mediumtall.jpg', 
        simgurl: 'https://www.apple.com/v/home/bo/images/heroes/ipad-pro/hero_ipadpro__bpt7a9d8sh42_small.jpg' 
      },
    ],
    addHeaderClass: true
  })
}
</script>
