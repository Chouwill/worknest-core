<template>
  <div class="bg-amber-200 flex justify-around items-center py-3">
    <div class="flex gap-3 border-4 ">
      <fieldset class="fieldset">
        <legend class="fieldset-legend">請選擇縣市</legend>
        <select class="select border border-white" v-model="selectedCity">
          <option disabled value="">請選擇縣市</option>
          <option v-for="item in cityOptions" :key="item.id" :value="item.cityName">
            {{ item.cityName }}
          </option>
        </select>
      </fieldset>
      <fieldset class="fieldset">
        <legend class="fieldset-legend">請選擇縣市</legend>
        <select class="select border border-white" v-model="selectedCity">
          <option disabled value="">請選擇縣市</option>
          <option v-for="item in cityOptions" :key="item.id" :value="item.cityName">
            {{ item.cityName }}
          </option>
        </select>
      </fieldset>
    </div>
    <div class="flex gap-2 items-center">
      <input
        type="checkbox"
        checked="checked"
        class="checkbox checkbox-md border-black border-2 rounded-xs"
      />
      <div>是否有插座</div>
    </div>
    <div>
      <label class="input">
        <svg class="h-[1em] opacity-50" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
          <g
            stroke-linejoin="round"
            stroke-linecap="round"
            stroke-width="2.5"
            fill="none"
            stroke="currentColor"
          >
            <circle cx="11" cy="11" r="8"></circle>
            <path d="m21 21-4.3-4.3"></path>
          </g>
        </svg>
        <input type="search" required placeholder="搜尋店名或地址" />
      </label>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const selectedCity = ref('')

const cityOptions = ref([
  {
    id: 1,
    cityName: '台北市',
  },
  {
    id: 2,
    cityName: '新北市',
  },
])
</script>
