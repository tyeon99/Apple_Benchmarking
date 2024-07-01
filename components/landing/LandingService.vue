<template>
  <section class="landingService">
    <div class="serviceBox box01">
      <div class="title">대학생</div>
      <div class="txt">Mac 그리고 iPad.훌쩍 앞서다.</div>
      <div class="btnGroup">
        <button>더 알아보기</button>
      </div>
    </div>
    <div class="serviceBox box02">
      <div class="title">MacBook Air</div>
      <div class="txt">날렵하게.강력하게.M3답게</div>
      <div class="btnGroup">
        <button>더 알아보기</button>
        <button>구입하기</button>
      </div>
    </div>
    <div class="serviceBox box03">
      <div class="title">
        <img class="largeImg" src="https://www.apple.com/v/home/bo/images/logos/apple-watch-series-9/promo_logo_apple_watch_series_9__ckz0hbex0yeu_large.png">
        <img src="https://www.apple.com/v/home/bo/images/logos/apple-watch-series-9/promo_logo_apple_watch_series_9__ckz0hbex0yeu_medium.png" class="mediumImg">
      </div>
      <div class="txt">보다 똑똑.보다 또렷.보다 강력</div>
      <div class="btnGroup">
        <button>더 알아보기</button>
        <button>구입하기</button>
      </div>
    </div>
    <div class="serviceBox box04">
      <div class="title">
        <img class="largeImg" src="https://www.apple.com/v/home/bo/images/logos/ipad-air/promo_logo_ipadair__frwnnsqveeye_large.png">
        <img src="https://www.apple.com/v/home/bo/images/logos/ipad-air/promo_logo_ipadair__frwnnsqveeye_medium.png" class="mediumImg">
      </div>
      <div class="txt">두 가지 사이즈.더 빠른 칩.무엇이든 거뜬하게.</div>
      <div class="btnGroup">
        <button>더 알아보기</button>
        <button>구입하기</button>
      </div>
    </div>
    <div class="serviceBox box05">
      <div class="title">App Store</div>
      <div class="txt">모이자,즐기자! 스쿼드 버스터즈.</div>
      <div class="btnGroup">
        <button>더 알아보기</button>
      </div>
    </div>
    <div class="serviceBox box06">
      <div class="title">
        <img class="largeImg" src="https://www.apple.com/v/home/bo/images/logos/iphone-tradein/logo_tradein__d1fpktgipvki_large.png">
        <img src="https://www.apple.com/v/home/bo/images/logos/iphone-tradein/logo_tradein__d1fpktgipvki_medium.png" class="mediumImg">
      </div>
      <div class="txt">iPhone 11 이상의 모델을 보상 판매하면 <br>₩200,000-₩950,000 <br>상당의 크레딧이. </div>
      <div class="btnGroup">
        <button>견적 확인하기</button>
      </div>
    </div>
  </section>
</template>

<script>
export default {

}
</script>

<style scoped>
.landingService{
  @apply w-full p-[12px] bg-[#fff] grid grid-cols-2 gap-[12px];
}
.serviceBox{
  @apply w-full h-[580px] flex flex-col justify-start items-center p-[40px];
}
.serviceBox.box01{
  @apply bg-[url('https://www.apple.com/v/home/bo/images/promos/college-students/promo_college_students__bxqdcoxgjzw2_large.jpg')] bg-center justify-end bg-no-repeat;
}
.serviceBox.box02{
  @apply bg-[url('https://www.apple.com/v/home/bo/images/promos/macbook-air-m3/promo_macbook_air_m3__e43jegok3wuq_large.jpg')] bg-center bg-no-repeat;
}
.serviceBox.box03{
  @apply bg-[url('https://www.apple.com/kr/home/bo/images/promos/apple-watch-series-9/promo_apple_watch_series_9_order__b3u85rm9zf6u_large.jpg')] bg-center bg-no-repeat;
}
.serviceBox.box04{
  @apply bg-[url('https://www.apple.com/v/home/bo/images/promos/ipad-air/promo_ipadair__cu1bnxi7uuwm_large.jpg')] bg-center bg-no-repeat;
}
.serviceBox.box05{
  @apply bg-[url('https://www.apple.com/v/home/bo/images/promos/app-store-squad-busters/promo_app_store_sb__b8zuxx50qely_large.jpg')] bg-center bg-no-repeat;
}
.serviceBox.box06{
  @apply bg-[url('https://www.apple.com/v/home/bo/images/promos/iphone-tradein/promo_iphone_tradein__bugw15ka691e_large.jpg')] bg-center bg-no-repeat;
}
.serviceBox .title {
  @apply text-[40px] text-[#fff] font-bold mb-[4px];
}
.serviceBox .title img{
  @apply mb-[10px];
}
.serviceBox .title img.largeImg{
  @apply block;
}
.serviceBox .title img.mediumImg{
  @apply hidden;
}
.serviceBox .txt {
  @apply text-[21px] mb-[15px] text-[#fff] font-normal text-center;
}
.serviceBox:nth-child(2n) .title,
.serviceBox:nth-child(2n) .txt {
  @apply text-[#1d1d1f];
}
.serviceBox .btnGroup {
  @apply flex justify-center items-center gap-[10px];
}
.serviceBox .btnGroup button {
  @apply text-[#2997ff] font-normal border border-[#2997ff] rounded-[30px] text-[14px] p-[7px_15px] first:text-[#fff] first:bg-[#0071e3] first:border-[#0071e3];
}
.serviceBox.box05 .btnGroup button {
  @apply bg-[#fff] text-[#1d1d1f]
}
@media (max-width: 1068px) {
  .serviceBox{
    @apply !h-[490px];
  }
  .serviceBox .title {
    @apply !text-[32px];
  }
  .serviceBox .txt{
    @apply !text-[19px];
  }
  .serviceBox .title img.largeImg{
    @apply hidden;
  }
  .serviceBox .title img.mediumImg{
    @apply block;
  }
  .serviceBox.box01{
    @apply !bg-[url('https://www.apple.com/v/home/bo/images/promos/college-students/promo_college_students__bxqdcoxgjzw2_medium.jpg')];
  }
  .serviceBox.box02{
    @apply !bg-[url('https://www.apple.com/v/home/bo/images/promos/macbook-air-m3/promo_macbook_air_m3__e43jegok3wuq_medium.jpg')];
  }
  .serviceBox.box03{
    @apply !bg-[url('https://www.apple.com/kr/home/bo/images/promos/apple-watch-series-9/promo_apple_watch_series_9_order__b3u85rm9zf6u_medium.jpg')];
  }
  .serviceBox.box04{
    @apply !bg-[url('https://www.apple.com/v/home/bo/images/promos/ipad-air/promo_ipadair__cu1bnxi7uuwm_medium.jpg')];
  }
  .serviceBox.box05{
    @apply !bg-[url('https://www.apple.com/v/home/bo/images/promos/app-store-squad-busters/promo_app_store_sb__b8zuxx50qely_medium.jpg')];
  }
  .serviceBox.box06{
    @apply !bg-[url('https://www.apple.com/v/home/bo/images/promos/iphone-tradein/promo_iphone_tradein__bugw15ka691e_medium.jpg')];
  }
}
@media (max-width: 734px) {
  .landingService{
    @apply !grid-cols-1;
  }
  .serviceBox{
    @apply !p-[30px];
  }
  .serviceBox .title {
    @apply !text-[32px];
  }
  .serviceBox .txt{
    @apply !text-[19px];
  }
  .serviceBox.box01{
    @apply !bg-[url('https://www.apple.com/v/home/bo/images/promos/college-students/promo_college_students__bxqdcoxgjzw2_small.jpg')];
  }
  .serviceBox.box02{
    @apply !bg-[url('https://www.apple.com/v/home/bo/images/promos/macbook-air-m3/promo_macbook_air_m3__e43jegok3wuq_small.jpg')];
  }
  .serviceBox.box03{
    @apply !bg-[url('https://www.apple.com/kr/home/bo/images/promos/apple-watch-series-9/promo_apple_watch_series_9_order__b3u85rm9zf6u_small.jpg')];
  }
  .serviceBox.box04{
    @apply !bg-[url('https://www.apple.com/v/home/bo/images/promos/ipad-air/promo_ipadair__cu1bnxi7uuwm_small.jpg')];
  }
  .serviceBox.box05{
    @apply !bg-[url('https://www.apple.com/v/home/bo/images/promos/app-store-squad-busters/promo_app_store_sb__b8zuxx50qely_small.jpg')];
  }
  .serviceBox.box06{
    @apply !bg-[url('https://www.apple.com/v/home/bo/images/promos/iphone-tradein/promo_iphone_tradein__bugw15ka691e_small.jpg')];
  }
}
</style>
