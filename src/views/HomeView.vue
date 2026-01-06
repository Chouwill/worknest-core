<script setup lang="ts">
import HomeContent from '@/components/HomePage/HomeContent.vue'
import HomeFilterForm from '@/components/HomePage/HomeFilterForm.vue'
import StoreCardList from '@/components/HomePage/StoreCardList.vue';
</script>

<template>
  <div class="contciner">
    <HomeContent />
    <HomeFilterForm />
    <StoreCardList />
  </div>
</template>
