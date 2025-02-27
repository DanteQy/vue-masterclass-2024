<script setup lang="ts">
import { usePageStore } from '@/stores/page'

const sheetopen = defineModel<boolean>()
</script>

<template>
  <Sheet v-model:open="sheetopen">
    <SheetContent>
      <SheetHeader>
        <SheetTitle>Create New Project</SheetTitle>
      </SheetHeader>
      <p>lalala</p>
    </SheetContent>
  </Sheet>
</template>

<style scoped></style>
