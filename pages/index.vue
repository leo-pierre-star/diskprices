<template>
  <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-4">
    <UCard
      v-for="product in products"
      :key="product.id"
      class="overflow-hidden"
      :ui="{
        header: {
          base: 'overflow-hidden',
          background: '',
          padding: 'px-0 py-0 sm:px-0',
        },
      }"
    >
      <template #header>
        <img
          class="object-cover aspect-video w-full"
          :src="product.image"
          :alt="product.title"
        />
      </template>

      <div class="flex flex-col gap-2">
        <h3 class="line-clamp-3 text-sm text-gray-500">{{ product.title }}</h3>
        <div class="text-pretty text-lg font-bold">
          {{ formatPrice(product.price) }}€
        </div>
        <UButton
          :ui="{ rounded: 'rounded-full' }"
          block
          icon="i-heroicons-pencil-square"
          size="sm"
          color="primary"
          variant="outline"
          label="Voir sur Amazon"
          :to="product.link"
          target="_blank"
          :trailing="false"
        />
      </div>
    </UCard>
  </div>
</template>

<script setup>
import products from "~/data/products";
import { formatPrice } from "~/core/helpers/price";

definePageMeta({
  layout: "default",
});
</script>
<style lang="scss" scoped>
.line-clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
