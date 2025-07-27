<script setup lang="ts">
const copyRight = 'CC BY-NC-SA 4.0 2019-PRESENT © Khaled Waleed'
</script>

<template>

    <main
      class="min-h-screen duration-300"
      bg="background dark:background-dark"
      px="6 lg:16 xxl:80"
      py="8"
      flex="~ col gap-16 xxl:justify-between"
    >
      <Header />

      <div
        flex="~ items-center"
        class="h-full xxl:mb-20"
      >
        <slot />
      </div>

      <span text="secondary-text dark:secondary-text-dark xs sm:sm">
        Built by <a
          href="https://vitex.dev"
          target="_blank"
          class="text-white hover:text-[#22c55e] duration-500"
        >
          vitex.
        </a>
      </span>


    </main>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease-in-out;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
