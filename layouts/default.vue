<template>
  <div class="h-screen">
    <Header />
    <UContainer class="py-10">
      <slot />
    </UContainer>
    <footer class="fixed bottom-0 w-full">
      <UContainer>
        <div class="flex justify-center items-center gap-2 w-full py-2">
          <p class="text-xs text-gray-500">
            Ce site est supporté par des liens affiliés.
          </p>

          <UButton
            icon="i-heroicons:information-circle"
            size="xs"
            color="primary"
            variant="outline"
            label="En savoir plus"
            to="/faq"
            :trailing="false"
          />
        </div>
      </UContainer>
    </footer>
  </div>
</template>
<script setup lang="ts"></script>
