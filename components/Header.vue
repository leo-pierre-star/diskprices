<script setup lang="ts">
const colorMode = useColorMode();
const isDark = computed({
  get() {
    return colorMode.value === "dark";
  },
  set() {
    colorMode.preference = colorMode.value === "dark" ? "light" : "dark";
  },
});

onMounted(() => console.info(isDark.value));

const toggleColorMode = () => {
  isDark.value = !isDark.value;
};

const links = computed(() => {
  return [
    [
      {
        label: "Accueil",
        icon: "i-heroicons-home",
        to: "/",
      },
      {
        label: "FAQ",
        icon: "i-heroicons:question-mark-circle",
        to: "/faq",
      },
    ],
    [
      {
        label: "",
        icon: isDark.value
          ? "i-heroicons-sun-20-solid"
          : "i-heroicons-moon-20-solid",
        click: toggleColorMode,
      },
    ],
  ];
});
</script>

<template>
  <UHorizontalNavigation
    :links="links"
    class="border-b border-gray-200 dark:border-gray-800"
  />
</template>
