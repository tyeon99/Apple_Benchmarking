<template>
  <section class="landingProduct" :class="{ 'bg-02' : idx === 1 }">
    <div class="product">
      <div class="productName">
        {{ product.title }}
      </div>
      <div class="productTxt">
        {{ product.txt }}
      </div>
      <div class="productBtn">
        <button>더 알아보기</button>
        <button>구입하기</button>
      </div>
    </div>
    <div class="productImg">
      <img :src="product.imgurl" :alt="product.title" class="largeImg">
      <img :src="product.simgurl" :alt="product.title" class="smallImg">
    </div>
  </section>
</template>

<script>
export default {
  props: {
    product: {
      type: Object,
      require: true,
      default: undefined
    },
    idx: {
      type: Number,
      require: true,
      default: undefined
    }
  },
}
</script>

<style scoped>
.landingProduct{
  @apply w-full h-[700px] relative flex flex-col justify-end items-center bg-[#000] overflow-hidden;
}
.bg-02{
  @apply !bg-[#f5f5f7];
}
.product{
  @apply w-full pt-[55px] text-center absolute top-0;
}
.productName{
  @apply text-[56px] font-bold text-[#fff] mb-[6px];
}
.productTxt{
  @apply text-[28px] font-normal text-[#fff] mb-[18px];
}
.landingProduct.bg-02 .productName, .landingProduct.bg-02 .productTxt{
  @apply text-[#1d1d1f];
}
.productImg img.largeImg{
  @apply block;
}
.productImg img.smallImg{
  @apply hidden;
}
.productBtn{
  @apply flex justify-center items-center gap-[15px];
}
.productBtn button{
  @apply text-[#2997ff] font-normal border border-[#2997ff] rounded-[30px] text-[17px] p-[11px_21px] first:text-[#fff] first:bg-[#0071e3] first:border-[#0071e3];
}
@media (max-width: 1068px) {
  .landingProduct{
    @apply h-[650px];
  }
  .productName{
    @apply text-[48px] mb-[5px];
  }
  .productTxt{
    @apply text-[24px];
  }
}
@media (max-width: 734px) {
  .landingProduct{
    @apply h-[500px];
  }
  .productName{
    @apply text-[32px] mb-[4px];
  }
  .productTxt{
    @apply text-[19px] mb-[17px];
  }
  .productImg img.largeImg {
    @apply hidden;
  }
  .productImg img.smallImg {
    @apply block;
  }
  .productBtn button{
    @apply text-[14px] p-[7px_15px];
  }
}
</style>