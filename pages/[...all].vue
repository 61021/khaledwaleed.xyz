<script setup lang="ts">
const router = useRouter()
</script>

<template>
  <main
  class="flex flex-col items-center justify-center h-full w-full"
  text="center teal-700 dark:gray-200">
    <div text-4xl>
      <div i-ph-warning-circle inline-block />
    </div>
    <div>Page Not found</div>
    <div>
      <button text-sm btn m="3 t8" 
      @click="router.back()">
        Back
      </button>
    </div>
  </main>
</template>
