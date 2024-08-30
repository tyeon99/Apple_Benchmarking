<template>
  <div class="storeMain">
    <StoreTitle />
    <StoreFooter />
  </div>
</template>

<script>
export default {
  layout: 'default',
  data: () => ({
    addHeaderClass: false,
    gyHeaderClass: true
  })
}
</script>
