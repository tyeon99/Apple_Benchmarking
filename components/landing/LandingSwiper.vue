<template>
  <div class="landingSwiper">
    <div class="swiper ldSwiper">
      <div class="swiper-wrapper">
        <div v-for="(slide, idx) in slides" :key="idx" class="swiper-slide">
          <img :src="slide.xlimgurl" class="xlImg img">
          <img :src="slide.limgurl" class="lImg img">
          <img :src="slide.mimgurl" class="mImg img">
          <div class="cropping">
            <img :src="slide.simgurl" class="sImg img">
            <div class="appleTv">
              <img width="68" src="https://www.apple.com/v/home/bo/images/tv-plus-gallery/logo_hero_light__d7t8cya4x26a_small.png" alt="애플티비 로고" class="logo">
              <img :src="slide.simgtitle" class="title">
            </div>
          </div>
          <div class="txt">
            <button>지금 시청하기</button>
            <div class="max-flex">
              <strong>{{ slide.category }}</strong>
              <em class="min-none">·</em><br class="max-none">
              <span>{{ slide.txt }}</span>
            </div>
          </div>
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
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features116/v4/f6/de/e4/f6dee492-57e7-3f37-8947-e0aae00d83d9/1fd19741-c5a8-4563-9013-9bac6e5432e1.png/274x593.jpg',
        category: '드라마',
        txt: '스티븐 스필버그,톰 행크스, 게리 고츠만 제작',
        simgtitle: 'https://is1-ssl.mzstatic.com/image/thumb/imsrhtWw0__R0NLI9szOGQ/548x145.png'
      },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/M6LUYgWMtdLDFGpdRz6OKQ/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/M6LUYgWMtdLDFGpdRz6OKQ/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/M6LUYgWMtdLDFGpdRz6OKQ/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features116/v4/7a/6d/da/7a6ddaf8-67fb-5e36-009e-fb833052139e/4cc4fe3a-9966-475d-8254-9e41ce6d6281.png/274x593.jpg',
        category: '코미디',
        txt: '매튜 본 감독 신작 스파일 스릴러',
        simgtitle: 'https://is1-ssl.mzstatic.com/image/thumb/v64262-YWaZqmhiuQrEG6w/548x193.png' 
      },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/Wf0pP4T72Imm2Solr-VB3g/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/Wf0pP4T72Imm2Solr-VB3g/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/Wf0pP4T72Imm2Solr-VB3g/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features/v4/d1/f8/6d/d1f86d5f-824e-f429-c7ea-fb52f13d557c/6fd7c8fd-6591-4b7c-8672-c3493200e2e0.png/274x593.jpg',
        category: '드라마',
        txt: '존재 자체가 미스터리인 사람이 있다',
        simgtitle: 'https://is1-ssl.mzstatic.com/image/thumb/M5H2657RdxxWfnRidD2Sgw/548x341.png'
      },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/fFOltSfH_F9HhYQHU1yDeg/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/fFOltSfH_F9HhYQHU1yDeg/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/fFOltSfH_F9HhYQHU1yDeg/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features126/v4/3d/53/b8/3d53b8f6-d02a-e9d5-1574-9da60301b158/b73a724a-f2be-4f73-b3cf-3ed351e65696.png/274x593.jpg', 
        category: '애니메이션',
        txt: '따뜻한 우정,끝없는 상상,신나는 모험!',
        simgtitle: 'https://is1-ssl.mzstatic.com/image/thumb/IEk0LbqotmuVLnINPau1uw/548x218.png'
      },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/I25UvCTJzFPQZ7dAB6BFRg/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/I25UvCTJzFPQZ7dAB6BFRg/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/I25UvCTJzFPQZ7dAB6BFRg/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features211/v4/15/23/9c/15239cd8-7f8f-aaa2-c745-6a0131e8ee50/814b5029-5162-468b-b8bd-7406d77fa224.png/274x593.jpg',
        category: '드라마',
        txt: '4개의 세대.하나의 운명.',
        simgtitle: 'https://is1-ssl.mzstatic.com/image/thumb/QjRiAXt4hA0ChHEKP2oO1A/548x304.png'
      },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/RYnkxE0RhDg4woUpaghtTg/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/RYnkxE0RhDg4woUpaghtTg/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/RYnkxE0RhDg4woUpaghtTg/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features126/v4/cd/35/da/cd35dae4-082f-ab31-16fd-227ac3998d8f/5a2094f5-11ee-48e2-836a-6f952b0a108c.png/274x593.jpg',
        category: '다큐멘터리',
        txt: '완전한 미지의 영역,드디어 베일을 벗다',
        simgtitle: 'https://is1-ssl.mzstatic.com/image/thumb/Vv52F_hKgjdcPhGKc578eA/548x157.png'
      },
      { 
        xlimgurl:'https://is1-ssl.mzstatic.com/image/thumb/gMjB2Z2TTM1gsL5A_rGAKw/1250x703.jpg',
        limgurl:'https://is1-ssl.mzstatic.com/image/thumb/gMjB2Z2TTM1gsL5A_rGAKw/980x551.jpg',  
        mimgurl:'https://is1-ssl.mzstatic.com/image/thumb/gMjB2Z2TTM1gsL5A_rGAKw/689x387.jpg',  
        simgurl:'https://is1-ssl.mzstatic.com/image/thumb/Features126/v4/50/fa/dd/50fadd09-3f39-0d32-3c57-a143e024a7a2/472f4d54-599f-49de-9f6f-1efd14d157ec.png/274x593.jpg',
        category: 'SF',
        txt: '진실은 결국 스스로를 드러낸다',
        simgtitle: 'https://is1-ssl.mzstatic.com/image/thumb/kpvXgLkR-rM_h3nq46yjAg/548x77.png'
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
      },
      on: {
        slideChange: function() {
          this.slides.forEach(slide => {
            const txtElement = slide.querySelector('.txt');
            const imgElements = slide.querySelectorAll('.img'); 
            if (txtElement) {
              txtElement.classList.remove('txtAni');
            }
            imgElements.forEach(img => { 
              img.classList.remove('brightness');
            });
          });
          
          const activeSlide = this.slides[this.activeIndex];
          const txtElement = activeSlide.querySelector('.txt');
          const imgElements = activeSlide.querySelectorAll('.img'); 
          if (txtElement) {
            txtElement.classList.add('txtAni');
          }
          imgElements.forEach(img => { 
            img.classList.add('brightness');
          });
        }
      }
    });
  }
}
</script>

<style scoped>
.swiper-slide{
  @apply relative flex justify-center items-center w-auto opacity-50;
}
.swiper-button-next, .swiper-button-prev{
  @apply text-[#868686]
}
.swiper-pagination{
  @apply relative mt-[20px];
}
.swiper-slide.swiper-slide-active{
  @apply opacity-100
}
.xlImg, .min-none{
  @apply block;
}
.lImg, .max-none, .mImg, .sImg{
  @apply hidden;
}
.appleTv{
  @apply hidden;
}
img.brightness{
  @apply animate-[dark_0.5s_ease-in-out] brightness-[0.9];
}
@keyframes dark{
  0% {
    filter: brightness(1.0);
  }
  100% {
    filter: brightness(0.9);
  }
}
.max-flex{
  @apply flex text-[20px] font-normal text-[#fff];
}
.txt{
  @apply absolute hidden items-center bottom-[40px] left-[45px];
}
.txt.txtAni{
  @apply flex animate-[txtup_0.3s_ease-in-out];
}
.txt button{
  @apply text-[17px] font-normal p-[11px_21px] bg-[#fff] text-[#161617] rounded-[30px] mr-[18px];
}
@keyframes txtup{
  0%{
    bottom: 0px;
    opacity: 0;
  }
  100%{
    bottom: 40px;
    opacity: 1;
  }
}
@media (max-width: 1440px) {
  .xlImg, .mImg, .sImg{
    @apply hidden;
  }
  .lImg{
    @apply block;
  }
}
@media (max-width: 1068px) {
  .xlImg, .lImg, .sImg{
    @apply hidden;
  }
  .mImg{
    @apply block;
  }
  .max-flex{
    @apply text-[17px];
  }
  .txt{
    @apply bottom-[25px] left-[30px];
  }
  .txt button{
    @apply text-[14px] p-[7px_15px];
  }
  @keyframes txtup{
  0%{
    bottom: 0px;
    opacity: 0;
  }
  100%{
    bottom: 25px;
    opacity: 1;
  }
}
}
@media (max-width: 734px) {
  .xlImg, .lImg, .mImg, .min-none{
    @apply hidden;
  }
  .sImg, .max-none, .max-flex{
    @apply block;
  }
  .cropping{
    @apply relative overflow-hidden max-h-[495px]
  }
  .appleTv{
    @apply absolute top-[20px] flex flex-col w-[274px] items-center gap-[8px];
  }
  .appleTv img.title{
    @apply h-[54px] object-contain;
  }
  .txt{
    @apply flex-col-reverse bottom-[30px] left-0 w-[274px];
  }
  .max-flex{
    @apply text-[15px] p-[0px_15px] text-center mb-[12px];
  }
  .txt button{
    @apply mr-0
  }
  @keyframes txtup{
  0%{
    bottom: 0px;
    opacity: 0;
  }
  100%{
    bottom: 30px;
    opacity: 1;
  }
}
}
</style>
