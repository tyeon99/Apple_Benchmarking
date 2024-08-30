<template>
  <div id="wrap">
    <GlobalHeader 
      :class="{ 'darkHeader': addHeaderClass, 'grayHeader': gyHeaderClass }"  
      @toggleDropdown="toggleDropdown" 
    />
    <div ref="Top"></div>
    <div id="content" :class="{ 'blur': isDropdownOpen }">
      <Nuxt />
    </div>
  </div>
</template>

<script>
export default{
  data: () => ({
    isDropdownOpen: false,
  }),
  computed: {
    addHeaderClass() {
      return this.$route.matched.some(record => record.components.default.options.data && record.components.default.options.data().addHeaderClass);
    },
    gyHeaderClass() {
      return this.$route.matched.some(record => record.components.default.options.data && record.components.default.options.data().gyHeaderClass);
    }
  },
  watch: {
    '$route' () {
      this.scrollToTop();
    }
  },
  methods: {
    scrollToTop() {
      this.$refs.Top.scrollIntoView();
    },
    toggleDropdown(state) {
      this.isDropdownOpen = state;
    }
  }
}
</script>

<style scoped>
#wrap {
  @apply w-full;
}
.blur {
  filter: blur(8px);
  background: rgba(0, 0, 0, 0.1); /* Temporary for testing */
}
</style>
