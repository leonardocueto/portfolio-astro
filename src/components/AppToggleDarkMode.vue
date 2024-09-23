<template>
  <button
    class="p-2 bg-gray-200 hover:bg-gray-300 dark:bg-gray-700 dark:hover:bg-gray-300 rounded-full transition-all hover:scale-110"
    @click="toggleDarkMode()"
  >
    <component
      :is="iconComponent"
      :key="iconComponent"
      color="gray"
      :size="25"
    />
  </button>
</template>
<script lang="ts" setup>
import { IconSun, IconMoon } from "@tabler/icons-vue";
import { computed, ref } from "vue";

const darkMode = ref(false);
const iconComponent = computed(() => (darkMode.value ? IconSun : IconMoon));
const toggleDarkMode = () => {
  const element = document.querySelector("html");
  element?.classList.toggle("dark");
  darkMode.value = !darkMode.value;
};
</script>
