<template>
  <div class="SiteGrid">
    <SiteItem v-for="site in sites" :key="site.host" :site="site" />
  </div>
</template>

<script setup>
import SiteItem from '@components/SiteItem.vue';

defineProps({
  sites: {
    type: Array,
    required: true,
  },
});
</script>

<style scoped>
div {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(36rem, 1fr));
  grid-auto-rows: minmax(20rem, 1fr);
  gap: 1.2rem;
  padding: 0;
}

@media (max-width: 560px) {
  div {
    grid-template-columns: 1fr;
    grid-auto-rows: min-content;
    gap: 0;
  }
}
</style>
