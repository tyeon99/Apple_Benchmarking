<template>
  <div class="footerNav">
    <div
      v-for="(navBox, idx) in menus"
      :key="idx"
      class="navBox"
    >
      <div
        v-for="(category, catIdx) in navBox"
        :key="catIdx"
        class="category"
      >
        <button
          class="title"
          :class="{ '!border-b-0' : isCategoryOpen(idx, catIdx) }"
          @click="toggleCategory(idx, catIdx)"
        >
          {{ category.title }}
        </button>
        <ul class="maxCategory">
          <li
            v-for="(item, itemIdx) in category.items" 
            :key="itemIdx"
          >
            {{ item }}
          </li>
        </ul>
        <ul v-show="isCategoryOpen(idx, catIdx)" class="minCategory">
          <li
            v-for="(item, itemIdx) in category.items" 
            :key="itemIdx"
          >
            {{ item }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menus: [
        [
          {
            title: "쇼핑 및 알아보기",
            items: ["스토어", "Mac", "iPad", "iPhone", "Watch", "AirPods", "TV 및 홈", "AirTag", "액세서리"]
          },
          {
            title: "Apple 지갑",
            items: ["지갑", "Apple Pay"]
          }
        ],
        [
          {
            title: "계정",
            items: ["Apple ID 관리", "Apple Store 계정", "iCloud.com"]
          },
          {
            title: "엔터테인먼트",
            items: ["Apple One", "Apply TV+", "Apple Music", "Apple Arcade", "Apple Podcasts", "Apple Books", "App Store"]
          }
        ],
        [
          {
            title: 'Apple Store',
            items: ['매장 찾기', 'Genius Bar', 'Today at Apple', '그룹 예약', 'Apple 캠프', 'Apple Store 앱', '인증 리퍼비쉬 제품', 'Apple Trade in', '할부 방식', '주문 상태', '쇼핑 도움말']
          }
        ],
        [
          {
            title: '비즈니스',
            items: ['Apple과 비즈니스', '비즈니스를 위한 제품 쇼핑하기']
          },
          {
            title: '교육',
            items: ['Apple과 교육', '초중고용 제품 쇼핑하기', '대학 생활을 위한 제품 쇼핑하기']
          }
        ],
        [
          {
            title: 'Apple의 가치관',
            items: ['손쉬운 사용', '교육', '환경', '개인정보 보호', '공급망']
          },
          {
            title: 'Apple 정보',
            items: ['Newsroom', 'Apple 리더십', '채용안내', '윤리 및 규정 준수', '이벤트', '일자리 창출', 'Apple 연락처']
          }
        ]
      ],
      openCategories: {}
    };
  },
  methods: {
  toggleCategory(navBoxIndex, categoryIndex) {
    if (window.innerWidth <= 734) {
      const key = `${navBoxIndex}-${categoryIndex}`;
      this.$set(this.openCategories, key, !this.openCategories[key]);
    }
  },
  isCategoryOpen(navBoxIndex, categoryIndex) {
    const key = `${navBoxIndex}-${categoryIndex}`;
    return !!this.openCategories[key];
  }
}
}
</script>

<style scoped>
.footerNav {
  @apply w-full p-[20px_0_40px] flex items-start justify-between;
}
.navBox{
  @apply w-[calc(100%/5)] flex flex-col gap-[25px];
}
.title{
  @apply w-full text-left text-[12px] leading-[1.3] font-bold text-[rgba(0,0,0,0.88)] mb-[10px];
}
.category ul li{
  @apply mb-[10px] last:mb-0 text-[rgba(0,0,0,0.72)] text-[12px] leading-[1.3] font-medium cursor-pointer;
}
@media (max-width: 734px) {
  .footerNav{
    @apply block;
  }
  .navBox{
    @apply w-full gap-0
  }
  .title{
    @apply m-0 h-[36px] border-b-[1px] border-[rgba(0,0,0,0.16)] relative;
  }
  .title::after {
    @apply content-[''] absolute right-[10px] top-[13px] border-r-[1px] border-b-[1px] border-[rgba(0,0,0,0.88)] inline-block p-[3px] rotate-[45deg];
  }
  .maxCategory{
    @apply hidden;
  }
  .category ul{
    @apply p-[5px_0_16px] border-b-[1px] border-[rgba(0,0,0,0.16)];
  }
  .category ul li{
    @apply p-[6px_14px]
  }
}
</style>
