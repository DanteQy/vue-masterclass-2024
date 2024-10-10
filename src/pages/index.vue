<script setup lang="ts"></script>

<template>
  <div>
    <h1>Home Page</h1>
    <RouterLink :to="{ name: '/projects/[id]', params: { id: 1 } }">Go to Project 1</RouterLink>
    <br />
    <RouterLink :to="'/projects'">Go to Projects</RouterLink>
    <br />
    <RouterLink :to="'/tasks'">Go to Tasks</RouterLink>
  </div>
</template>
