<script setup lang="ts">
const heading = 'Khaled Waleed'

import { appName, appDescription } from '../constants'


defineOgImageComponent('NuxtSeo', {
  title: appName,
  description: appDescription,
  theme: '#0ea5e9',
  colorMode: 'dark',
})

const isFullScreen = ref(false)
</script>

<template>
  <main
    flex="~ gap4 lg:gap12 xxl:gap16 items-center col lg:row-reverse lg:justify-between"
    class="h-full w-full"
  >
    <NuxtImg
      class="aspect-square w-full object-cover"
      bg="background dark:background-dark"
      src="/images/khaled-waleed.jpg"
      alt="Khaled Waleed Portrait"
      w="lg:120"

      :class="{
        'h-screen! xxl:w-full! object-contain! border-0! top-0! left-0! z55! fixed!': isFullScreen,
      }"
      border="2 transparent dark:primary-text-dark"
      @click="isFullScreen = !isFullScreen"
      placeholder
    />
    <div
      flex="~ col gap12 lg:gap32"
      w="xxl:full"
    >
      <div flex="~ gap4 xxl:gap6 col">
        <h1
          class="font-bold duration-300"
          mt="4 lg:0"
          text="4xl lg:5xl xxl:6xl"
          v-text="heading"
        />

        <p
          text="secondary-text xxl:lg dark:secondary-text-dark"
          class="duration-300"
        >
        Digital Transformation Strategist at 
          <a
            href="https://morshed-bdc.com"
            target="_blank"
            class="text-secondary-text font-bold duration-300 dark:text-secondary-text-dark hover:text-primary hover:dark:text-primary-dark"
          >
            Morshed Group
          </a>. I write about software, 
          <br>
          engineering, and digital transformation.

        </p>
      </div>
      <Socials />
    </div>
  </main>
</template>
