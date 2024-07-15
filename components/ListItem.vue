<script setup lang="ts"></script>

<template>
  <div class="w-full p-4 border border-b-gray-200 flex items-center justify-between">
    <span class="text-xl font-semibold">
      <slot />
    </span>

    <!--Botões de ação-->
    <div class="w-32 space-x-2">
      <slot name="actions" />
    </div>
  </div>
</template>

<style scoped></style>
