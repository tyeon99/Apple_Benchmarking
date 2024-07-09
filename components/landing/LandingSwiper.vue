<template>
  <div class="landingSwiper">
    <div class="swiper ldSwiper">
      <div class="swiper-wrapper">
        <div
          v-for="(slide, idx) in slides"
          :key="idx"
          class="swiper-slide"
        >
        <img :src="slide.xlimgurl" class="xlImg">
        <img :src="slide.limgurl" class="lImg">
        <img :src="slide.mimgurl" class="mImg">
        <img :src="slide.simgurl" class="sImg">
        </div>
      </div>
      <div class="swiper-pagination"></div>
      <div class="swiper-button-next"></div>
      <div class="swiper-button-prev"></div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    slides: [
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/PpNA7zp0nJJN23khb-XDUw/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/PpNA7zp0nJJN23khb-XDUw/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/PpNA7zp0nJJN23khb-XDUw/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features116/v4/f6/de/e4/f6dee492-57e7-3f37-8947-e0aae00d83d9/1fd19741-c5a8-4563-9013-9bac6e5432e1.png/274x593.jpg' },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/M6LUYgWMtdLDFGpdRz6OKQ/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/M6LUYgWMtdLDFGpdRz6OKQ/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/M6LUYgWMtdLDFGpdRz6OKQ/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features116/v4/7a/6d/da/7a6ddaf8-67fb-5e36-009e-fb833052139e/4cc4fe3a-9966-475d-8254-9e41ce6d6281.png/274x593.jpg' 
      },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/Wf0pP4T72Imm2Solr-VB3g/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/Wf0pP4T72Imm2Solr-VB3g/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/Wf0pP4T72Imm2Solr-VB3g/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features/v4/d1/f8/6d/d1f86d5f-824e-f429-c7ea-fb52f13d557c/6fd7c8fd-6591-4b7c-8672-c3493200e2e0.png/274x593.jpg' 
      },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/fFOltSfH_F9HhYQHU1yDeg/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/fFOltSfH_F9HhYQHU1yDeg/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/fFOltSfH_F9HhYQHU1yDeg/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features126/v4/3d/53/b8/3d53b8f6-d02a-e9d5-1574-9da60301b158/b73a724a-f2be-4f73-b3cf-3ed351e65696.png/274x593.jpg' 
      },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/I25UvCTJzFPQZ7dAB6BFRg/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/I25UvCTJzFPQZ7dAB6BFRg/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/I25UvCTJzFPQZ7dAB6BFRg/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features211/v4/15/23/9c/15239cd8-7f8f-aaa2-c745-6a0131e8ee50/814b5029-5162-468b-b8bd-7406d77fa224.png/274x593.jpg' 
      },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/RYnkxE0RhDg4woUpaghtTg/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/RYnkxE0RhDg4woUpaghtTg/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/RYnkxE0RhDg4woUpaghtTg/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features126/v4/cd/35/da/cd35dae4-082f-ab31-16fd-227ac3998d8f/5a2094f5-11ee-48e2-836a-6f952b0a108c.png/274x593.jpg' 
      },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/gMjB2Z2TTM1gsL5A_rGAKw/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/gMjB2Z2TTM1gsL5A_rGAKw/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/gMjB2Z2TTM1gsL5A_rGAKw/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features126/v4/50/fa/dd/50fadd09-3f39-0d32-3c57-a143e024a7a2/472f4d54-599f-49de-9f6f-1efd14d157ec.png/274x593.jpg' 
      }
    ]
  }),
  mounted() {
    // eslint-disable-next-line no-new
    new window.Swiper(".ldSwiper",{
      slidesPerView: 'auto',
      centeredSlides: true,
      spaceBetween: 30,
      loop: true,
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
      pagination: {
        el: ".swiper-pagination",
        clickable: true
      }
    });
  }
}
</script>

<style scoped>
.swiper-slide{
  @apply flex justify-center items-center w-auto opacity-50;
}
.swiper-button-next, .swiper-button-prev{
  @apply text-[#868686]
}
.swiper-pagination{
  @apply relative mt-[20px];
}
.swiper-pagination-bullet-active{
  @apply bg-[#161617]
}
.swiper-slide.swiper-slide-active{
  @apply opacity-100
}
.xlImg{
  @apply block;
}
.lImg{
  @apply hidden;
}
.mImg{
  @apply hidden;
}
.sImg{
  @apply hidden;
}
@media (max-width: 1440px) {
  .xlImg{
    @apply hidden;
  }
  .lImg{
    @apply block;
  }
  .mImg{
    @apply hidden;
  }
  .sImg{
    @apply hidden;
  }
}
@media (max-width: 1068px) {
  .xlImg{
    @apply hidden;
  }
  .lImg{
    @apply hidden;
  }
  .mImg{
    @apply block;
  }
  .sImg{
    @apply hidden;
  }
}
@media (max-width: 734px) {
  .xlImg{
    @apply hidden;
  }
  .lImg{
    @apply hidden;
  }
  .mImg{
    @apply hidden;
  }
  .sImg{
    @apply block;
  }
}
</style>
