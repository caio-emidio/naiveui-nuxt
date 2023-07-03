<template>
  <NaiveConfig :theme-config="themeConfig">
    <NaiveNavbar
      :routes="navbarRoutes"
      :menu-inverted="false"
      drawer-closable
      menu-placement="center"
    >
      <template #start>
        <nuxt-link to="/">
          <NaiveIcon name="logos:naiveui"></NaiveIcon>
          <n-text strong>nuxt-naiveui</n-text>
        </nuxt-link>
      </template>

      <template #end>
        <NuxtLink
          to="https://github.com/becem-gharbi/nuxt-naiveui"
          target="_"
          aria-label="source-code"
        >
          <n-button text tag="span">
            <NaiveIcon name="cib:github" />
          </n-button>
        </NuxtLink>
        <NaiveColorModeSwitch />
      </template>

      <template #drawer-header>
        <n-text>Header</n-text>
      </template>

      <template #drawer-footer>
        <n-text>Footer</n-text>
      </template>
    </NaiveNavbar>

    <NuxtPage></NuxtPage>

    <NaiveTabbar :routes="tabBarRoutes" />
  </NaiveConfig>
</template>

<script setup lang="ts">
import { definePageMeta } from '#imports';

definePageMeta({
  colorMode: "dark",
});

const navbarRoutes = [
  {
    label: "Sample, this is a long long lable",
    icon: "ri:home-4-line",
    path: "/",
  },
  {
    label: "Categories",
    icon: "mdi:bookmark-multiple-outline",
    children: [
      {
        label: "Books",
        icon: "material-symbols:menu-book-outline-rounded",
        path: "/books",
      },
      {
        label: "Computers",
        icon: "material-symbols:computer-outline",
        path: "/computers",
      },
    ],
  },
];

const tabBarRoutes = [
  {
    label: "Sample",
    iconUnselected: "ri:home-4-line",
    iconSelected: "material-symbols:home-sharp",
    path: "/",
  },
  {
    label: "Books",
    iconUnselected: "material-symbols:menu-book-outline-rounded",
    iconSelected: "material-symbols:menu-book-sharp",
    path: "/books",
  },
  {
    label: "Computers",
    iconUnselected: "material-symbols:computer-outline",
    iconSelected: "material-symbols:computer",
    path: "/computers",
  },
];

const themeConfig = {
  shared: {
    common: {
      fontFamily: "Gellix",
      fontSize: "1.2rem",
      primaryColor: "#8a2be2",
      primaryColorHover: "#7a1be2",
      primaryColorPressed: "#9C5BE2",
      primaryColorSuppl: "rgb(42, 148, 125)",
    },
  },
};
</script>

<style scoped>
.brand {
  display: flex;
  align-items: center;
  gap: 1em;
}
</style>
