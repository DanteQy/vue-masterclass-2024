<script setup lang="ts">
import AuthLayout from '@/components/Layout/main/AuthLayout.vue'
</script>

<template>
  <auth-layout>
    <main>
      <RouterView v-slot="{ Component, route }">
        <Suspense v-if="Component" #fallback>
          <Component :is="Component" :key="route.name"></Component>

          <template #fallback>
            <span>Loading ..</span>
          </template>
        </Suspense>
      </RouterView>
    </main>
  </auth-layout>
</template>
