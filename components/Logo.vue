<script setup lang="ts">
defineProps<{
  isDark?: boolean
}>()
</script>

<template>
  <NuxtLink
  to="/"
    class="relative"
    flex="~ items-center justify-center"
  >
    <svg width="100" height="100" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
      <g clip-path="url(#clip0_502_8)">
        <path fill-rule="evenodd" clip-rule="evenodd" d="M74.0028 57.7707C84.2585 57.7707 92.5723 49.483 92.5723 39.2596C92.5723 29.0362 84.2585 20.7485 74.0028 20.7485C63.7472 20.7485 55.4334 29.0362 55.4334 39.2596C55.4334 49.483 63.7472 57.7707 74.0028 57.7707ZM74.0028 65.1751C88.3607 65.1751 100 53.5723 100 39.2596C100 24.9469 88.3607 13.3441 74.0028 13.3441C59.645 13.3441 48.0056 24.9469 48.0056 39.2596C48.0056 53.5723 59.645 65.1751 74.0028 65.1751Z" class="fill-primary-text dark:fill-primary-text-dark" />
        <path d="M48.0056 81.444C48.0056 79.4122 49.6684 77.7651 51.7195 77.7651H96.2862C98.3373 77.7651 100 79.4122 100 81.444V81.444C100 83.4758 98.3373 85.1228 96.2862 85.1228H51.7195C49.6684 85.1228 48.0056 83.4758 48.0056 81.444V81.444Z" class="fill-primary-text dark:fill-primary-text-dark" />
        <path d="M1.08637 84.1337C-0.362123 82.6853 -0.362122 80.3368 1.08637 78.8883L32.559 47.4156C34.0075 45.9671 36.356 45.9671 37.8045 47.4156C39.253 48.8641 39.253 51.2126 37.8045 52.6611L6.33181 84.1337C4.88332 85.5822 2.53486 85.5822 1.08637 84.1337Z" class="fill-primary-text dark:fill-primary-text-dark" />
        <path d="M1.0864 15.8882C2.53489 14.4398 4.88335 14.4398 6.33184 15.8882L37.8045 47.3609C39.253 48.8094 39.253 51.1579 37.8045 52.6064C36.356 54.0549 34.0076 54.0549 32.5591 52.6064L1.0864 21.1337C-0.362092 19.6852 -0.362093 17.3367 1.0864 15.8882Z" class="fill-primary-text dark:fill-primary-text-dark" />
      </g>
      <defs>
        <clipPath id="clip0_502_8">
          <rect
            width="100" height="100"
            class="fill-primary-text dark:fill-primary-text-dark"
          />
        </clipPath>
      </defs>
    </svg>
  </NuxtLink>
</template>
