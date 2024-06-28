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
  @apply bg-[url('https://www.apple.com/v/home/bo/images/promos/college-students/promo_college_students__bxqdcoxgjzw2_large.jpg')] bg-center justify-end;
}
.serviceBox.box02{
  @apply bg-[url('https://www.apple.com/v/home/bo/images/promos/macbook-air-m3/promo_macbook_air_m3__e43jegok3wuq_large.jpg')] bg-center;
}
.serviceBox.box03{
  @apply bg-[url('https://www.apple.com/kr/home/bo/images/promos/apple-watch-series-9/promo_apple_watch_series_9_order__b3u85rm9zf6u_large.jpg')] bg-center;
}
.serviceBox.box04{
  @apply bg-[url('https://www.apple.com/v/home/bo/images/promos/ipad-air/promo_ipadair__cu1bnxi7uuwm_large.jpg')] bg-center;
}
.serviceBox.box05{
  @apply bg-[url('https://www.apple.com/v/home/bo/images/promos/app-store-squad-busters/promo_app_store_sb__b8zuxx50qely_large.jpg')] bg-center;
}
.serviceBox.box06{
  @apply bg-[url('https://www.apple.com/v/home/bo/images/promos/iphone-tradein/promo_iphone_tradein__bugw15ka691e_large.jpg')] bg-center;
}
</style>
