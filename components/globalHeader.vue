<script setup lang="ts">
defineProps(["navigation", "searchurl"]);
</script>
<template>
  <div class="sticky top-0 z-50">
    <header
      class="px-8 py-4 flex justify-between items-center bg-[#1b1d39] lg:bg-opacity-80 h-[91px]"
    >
      <NuxtLink
        to="/"
        class="home-button"
        title="Homepage"
        aria-label="Homepage"
      >
        <tim class="w-[43px] h-[61px]" />
      </NuxtLink>

      <input
        type="checkbox"
        id="menuToggle"
        class="hidden"
        aria-labelledby="open-menu"
      />

      <label
        for="menuToggle"
        class="nav-toggle z-[60] absolute top-8 right-8 w-8 h-8 lg:hidden transform transition duration-500 ease-in-out"
      >
        <span class="sr-only" id="open-menu">Open main menu</span>
        <div class="block w-8 h-8">
          <span
            class="line-1 bg-white translate-y-0 absolute block h-1 w-8 transform bg-primary transition duration-500 ease-in-out"
          ></span>
          <span
            class="line-2 bg-white translate-y-3 absolute block h-1 w-8 transform bg-primary transition duration-500 ease-in-out"
          ></span>
          <span
            class="line-3 bg-white translate-y-6 absolute block h-1 w-8 transform bg-primary transition duration-500 ease-in-out"
          ></span>
        </div>
      </label>

      <nav
        id="nav"
        class="absolute top-[91px] left-0 w-full z-50 lg:static bg-[#1b1d39] lg:bg-transparent"
      >
        <ul
          class="flex space-x-0 lg:space-x-8 justify-end items-center lg:items-baseline flex-col lg:flex-row"
        >
          <li
            v-for="link of navigation"
            :key="link.copy"
            class="font-bold uppercase mb-4 lg:mb-0"
          >
            <NuxtLink :to="link.url">{{ link.copy }}</NuxtLink>
          </li>
          <li
            class="font-bold uppercase lg:relative lg:top-1 mb-4 lg:mb-0"
            v-if="searchurl"
          >
            <NuxtLink
              :to="searchurl"
              class="flex space-x-2 lg:space-x-0 lg:block"
            >
              <span class="lg:hidden">SEARCH</span>
              <search />
            </NuxtLink>
          </li>
        </ul>
      </nav>
    </header>
    <slot></slot>
  </div>
</template>
