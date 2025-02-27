<script setup lang="ts">
import { menuKey } from '@/utils/injectionKeys'

const { pageData } = storeToRefs(usePageStore())

const taskSheetOpen = ref(false)
const projectSheetOpen = ref(false)
const { menuOpen } = useMenu()

const toggleMenu = () => (menuOpen.value = !menuOpen.value)
provide(menuKey, { menuOpen, toggleMenu })
</script>

<template>
  <Sidebar @taskClicked="taskSheetOpen = true" @projectClicked="projectSheetOpen = true" />
  <AppNewTask v-model="taskSheetOpen"></AppNewTask>
  <AppNewProject v-model="projectSheetOpen"></AppNewProject>

  <div class="flex flex-col transition-[margin]" :class="{ 'ml-52': menuOpen, 'ml-24': !menuOpen }">
    <TopNavbar />

    <main class="flex flex-col flex-1 gap-4 p-4 lg:gap-6 lg:p-6">
      <div class="flex items-center">
        <h1 class="text-lg font-semibold md:text-2xl">{{ pageData.title }}</h1>
      </div>
      <slot />
    </main>
  </div>
</template>
