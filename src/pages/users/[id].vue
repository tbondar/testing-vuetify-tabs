<template>
  <h2>User {{ id }}</h2>

  <v-tabs v-model="tab">
    <v-tab :to="`/users/${id}/one`" exact>One</v-tab>
    <v-tab :to="`/users/${id}/two`" exact>Two</v-tab>
    <v-tab :to="`/users/${id}/three`" exact>Three</v-tab>
  </v-tabs>

  <v-tabs-window v-model="tab">
    <v-tabs-window-item>
      <RouterView />
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
