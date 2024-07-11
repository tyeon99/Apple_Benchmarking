<template>
  <footer class="landingFooter">
    <div class="footer-content">
      <div class="footer-txt">
        1. Apple Intelligence는 Siri 및 기기 언어를 미국 영어로 설정한 iPhone 15 Pro, iPhone 15 Pro Max 그리고 M1 칩 이후 버전을 탑재한 iPad 및 Mac에서 베타로 사용할 수 있으며, 올 하반기 iOS 18, iPadOS 18, macOS Sequoia를 통해 제공됩니다. <br><br>
        2. ₩950,000은 iPhone 14 Pro Max 1TB 모델의 보상 판매 금액으로, 보상 판매 프로그램은 Apple의 파트너이자 독립적으로 운영되는 제3의 업체에 의해 제공됩니다. Apple 및 Apple의 계열사는 고객과 파트너 간 계약의 당사자가 아닙니다. 보상 판매 견적은 예상 금액이며 실제 보상 판매 금액은 예상 금액보다 낮을 수 있습니다. 보상 판매 금액은 보상 판매 대상이 되는 제품의 상태, 연도, 구성에 따라 달라집니다. 일부 기기는 보상 판매 대상이 아닙니다. 기기를 보상 판매 하려면 민법상 성년이어야 합니다. 보상 판매 금액은 적용 가능한 새 기기 구입 시 적용하거나 Apple Store Gift Card로 받을 수 있습니다. 최종 확정 금액은 보상 판매 대상 기기를 수령한 후, 예상 금액 산정 시 제시한 기기의 설명과 일치하는지 비교 검수 후 정해집니다. 부가세는 새로 구입한 기기의 총액을 바탕으로 부과됩니다. 일부 매장에서는 보상 판매를 제공하지 않으며, 매장 내 보상 판매와 온라인 보상 판매 프로그램 간 내용에 차이가 있을 수 있습니다. 일부 매장은 추가 요구 사항이 있을 수 있습니다. Apple의 보상 판매 파트너는 보상 판매 거래를 거부, 취소하거나 보상 판매 수량을 제한할 권리를 보유합니다. 적용 가능 기기의 보상 판매 및 재활용에 대한 자세한 내용은 Apple의 보상 판매 파트너사에서 확인할 수 있습니다. 규제 및 제한이 적용될 수 있습니다. <br><br>
        Apple TV+ 이용을 위해서는 구독이 필요합니다.
      </div>
      <FooterNav />
      <div class="etc">
        다양한 쇼핑 방법: <a href="#">Apple Store를 방문</a>하거나, <a href="#">리셀러</a>를 찾아보거나, 080-330-8877번으로 전화하세요.
      </div>
      <div class="copyright">
        <div>Copyright © 2024 Apple Inc. 모든 권리 보유.</div>
        <div class="menu">
          <button>개인정보처리방침</button>
          <button>웹 사이트 이용 약관</button>
          <button>판매 및 환불</button>
          <button>법적 고지</button>
          <button>사이트 맵</button>
        </div>
      </div>
      <div class="business-information">
        애플코리아 유한회사 | 대표이사: Peter R. Denwood | 주소: 서울특별시 강남구 영동대로 517 | 전화: 080-333-4000 | <a href="#">https://support.apple.com/ko-kr</a> | 사업자등록번호: 120-81-84429 | 통신판매업신고번호: 제2011-서울강남-00810호 | 호스팅 서비스 제공: Apple Inc. | <a href="#">사업자정보</a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  
}
</script>

<style scoped>
.landingFooter{
  @apply w-full bg-[#f5f5f7]
}
.footer-content{
  @apply max-w-[980px] p-[20px_22px] m-[0_auto];
}
.footer-txt, .etc{
  @apply text-[12px] leading-[1.3] font-medium text-[rgba(0,0,0,0.56)] pb-[20px] border-b-[1px] border-[rgba(0,0,0,0.16)];
}
.etc a{
  @apply text-[#0066cc] underline;
}
.copyright{
  @apply text-[12px] leading-[1.3] font-medium text-[rgba(0,0,0,0.56)] flex justify-start items-center gap-[30px] pt-[20px];
}
.copyright .menu{
  @apply flex flex-wrap gap-[10px];
}
.copyright .menu button{
  @apply pr-[10px] text-[rgba(0,0,0,0.72)] border-r-[1px] border-[rgba(0,0,0,0.48)] last:border-r-0;
}
.business-information{
  @apply text-[11px] text-[#999] font-medium leading-[1.3] pt-[20px];
}
.business-information a{
  @apply text-[rgba(0,0,0,0.72)] underline;
}
@media (max-width: 734px) {
  .footer-content{
    @apply p-[20px_17px];
  }
  .etc{
    @apply border-b-0 pb-0;
  }
  .copyright{
    @apply flex-col items-start gap-[10px];
  }
}
</style>