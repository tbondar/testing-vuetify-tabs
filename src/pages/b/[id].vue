<template>
  <h2>Tabs without routing (id = {{ id }})</h2>

  <v-tabs v-model="tab">
    <v-tab value="one">One</v-tab>
    <v-tab value="two">Two</v-tab>
    <v-tab value="three">Three</v-tab>
  </v-tabs>

  <v-tabs-window v-model="tab">
    <v-tabs-window-item value="one">
      <h1>ONE</h1>
    </v-tabs-window-item>
    <v-tabs-window-item value="two">
      <h1>TWO</h1>
    </v-tabs-window-item>
    <v-tabs-window-item value="three">
      <h1>THREE</h1>
    </v-tabs-window-item>
  </v-tabs-window>
</template>

<script setup>
  import { computed, ref } from 'vue'
  import { useRoute } from 'vue-router'

  const tab = ref(null)
  const route = useRoute()

  const id = computed(() => {
    return route.params.id
  })

</script>
