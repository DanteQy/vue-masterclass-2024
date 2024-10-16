<script setup lang="ts"></script>

<template>
  <AuthLayout>
    <RouterView v-slot="{ Component, route }">
      <Suspense v-if="Component">
        <Component :is="Component" :key="route.name"></Component>

        <template #fallback>
          <span>Loading ..</span>
        </template>
      </Suspense>
    </RouterView>
  </AuthLayout>
</template>
