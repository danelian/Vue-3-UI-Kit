<script setup>
  import {ref} from 'vue'
  import Radiobutton from '@/components/Radiobutton.vue'

  const footballClubs = ([
    {name: 'FC Barcelona', id: 'f1'},
    {name: 'Real Madrid', id: 'f2'},
    {name: 'AC Inter', id: 'f3'},
    {name: 'FC Ararat', id: 'f4'},
  ])
  const selectedClubs = ref('')

  const disabledRadio = ref(true)
  const disabledRabioChecked = ref(true)
</script>

<template>
  <h1 class="heading-1">Radiobutton</h1>
  <h2 class="heading-2">Basic</h2>
  <div class="line line_block">
    <p>Selected Club: {{selectedClubs}}</p>
    <div
      v-for="club in footballClubs"
      :key="club.id">
      <radiobutton
        :value="club.name"
        :label="club.name"
        :id="club.id"
        name="club"
        v-model:checkedValue="selectedClubs"
      />
    </div>
  </div>
  <h2 class="heading-2">Disabled</h2>
  <div class="line">
    <radiobutton
      value="Radiobutton Disabled"
      label="Radiobutton Disabled"
      id="RadiobuttonDisabled"
      name="adiobuttonDisabled"
      :disabled="disabledRadio"
      v-model:checkedValue="disabledRabioChecked"
    />
  </div>
</template>