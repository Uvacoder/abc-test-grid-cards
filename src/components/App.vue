<template>
  <div class="Wrapper">
    <Header />
    <SiteGrid :sites="sortedSites" />
    <Footer />
  </div>
</template>

<script setup>
import sortBy from 'lodash/sortBy';
import Header from '@components/Header.vue';
import Footer from '@components/Footer.vue';
import SiteGrid from '@components/SiteGrid.vue';
import sites from '@data/sites.json';

const siteExpiry = (site) => (site.expiry ? new Date(site.expiry) : null);
const sortedSites = sortBy(sites, ['status', siteExpiry, 'title']);
</script>

<style scoped>
.Wrapper {
  display: flex;
  flex-direction: column;
  gap: 2.4rem;
  padding: 2.4rem;
}

@media (max-width: 560px) {
  .Wrapper {
    padding-left: 0;
    padding-right: 0;
  }
}
</style>
