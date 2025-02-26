<template>
    <v-container>
      <v-row>
        <v-col v-for="product in products" :key="product.id" cols="12" md="6">
          <v-card>
            <v-img :src="product.image" height="200px" cover></v-img>
            <v-card-title>{{ product.title }}</v-card-title>
            <v-card-actions>
              <v-btn :href="product.link" target="_blank" color="primary">
                Voir sur Amazon
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
      <p>Ce site est supporté par des liens affiliés.</p>
      <v-btn to="/faq" color="primary" class="mb-4">
        ℹ En savoir plus
      </v-btn>
    </v-container>
  </template>
  

  <script setup>
  import products from '~/data/products';
</script>