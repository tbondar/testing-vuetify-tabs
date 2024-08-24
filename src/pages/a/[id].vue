<template>
  <h2>Tabs with routing (id = {{ id }})</h2>

  <v-tabs v-model="tab">
    <v-tab :to="`/a/${id}/one`" exact>One</v-tab>
    <v-tab :to="`/a/${id}/two`" exact>Two</v-tab>
    <v-tab :to="`/a/${id}/three`" exact>Three</v-tab>
  </v-tabs>

  <RouterView />
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
