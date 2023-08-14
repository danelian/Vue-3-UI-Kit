<script setup>
  import {ref} from 'vue'
  import Tabs from '@/components/Tabs.vue'

  const tabs = [
    {name: 'About', label: 'О проекте'},
    {name: 'Vue', label: 'Про Vue'},
    {name: 'React', label: 'Про React'},
  ]

  const selectedTab = ref('Vue')

  const changeTab = (tabName) => {
    selectedTab.value = tabName
  }
</script>

<template>
  <h1 class="heading-1">Tabs</h1>
  <Tabs
    :names="tabs"
    :selectedTab="selectedTab"
    @changeTab="changeTab">
    <div v-if="selectedTab === 'About'">
      lorem, ipsum dolor sit amet consectetur adipisicing elit.
    </div>
    <div v-if="selectedTab === 'Vue'">
      Dolor sit amet consectetur adipisicing elit.
    </div>
    <div v-if="selectedTab === 'React'">
      Consectetur adipisicing elit.
    </div>
  </Tabs>
</template>