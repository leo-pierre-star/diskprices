<script setup lang="ts">
const form = reactive({
  brands: [],
  sizes: [],
  productionLocations: [],
  unusedMaterials: [],
  materials: [],
});

const columns = [
  {
    key: "price_per_unit",
    label: "Prix/unité",
  },
  {
    key: "size",
    label: "Taille",
  },
  {
    key: "price",
    label: "Prix",
  },
  {
    key: "quantity",
    label: "Quantité",
  },
  {
    key: "affiliated_link",
    label: "Lien affilié",
  },
];

const resultGetter = [
  {
    price_per_unit: 0.2,
    size: "1",
    price: 10,
    quantity: 50,
    affiliated_link: "https://www.google.com",
  },
  {
    price_per_unit: 0.3,
    size: "2",
    price: 15,
    quantity: 50,
    affiliated_link: "https://www.google.com",
  },
  {
    price_per_unit: 0.4,
    size: "3",
    price: 20,
    quantity: 50,
    affiliated_link: "https://www.google.com",
  },
  {
    price_per_unit: 0.5,
    size: "4",
    price: 25,
    quantity: 50,
    affiliated_link: "https://www.google.com",
  },
  {
    price_per_unit: 0.6,
    size: "5",
    price: 30,
    quantity: 50,
    affiliated_link: "https://www.google.com",
  },
  {
    price_per_unit: 0.7,
    size: "6",
    price: 35,
    quantity: 50,
    affiliated_link: "https://www.google.com",
  },
  {
    price_per_unit: 0.8,
    size: "6+",
    price: 40,
    quantity: 50,
    affiliated_link: "https://www.google.com",
  },
  {
    price_per_unit: 0.9,
    size: "L/XL",
    price: 45,
    quantity: 50,
    affiliated_link: "https://www.google.com",
  },
];

const brands = [
  "Wade Cooper",
  "Arlene Mccoy",
  "Devon Webb",
  "Tom Cook",
  "Tanya Fox",
  "Hellen Schmidt",
  "Caroline Schultz",
  "Mason Heaney",
  "Claudie Smitham",
  "Emil Schaefer",
];

const sizes = ["0", "1", "2", "3", "4", "4+", "5", "6", "6+", "L/XL"];

const productionLocations = ["France", "Allemagne", "Italie"];

const unusedMaterials = [
  "Plastique",
  "Pétrole",
  "Coton",
  "Bois",
  "Métal",
  "Verre",
  "Papier",
  "Carton",
  "Tissu",
  "Caoutchouc",
];

const materials = [
  "Coton",
  "Bois",
  "Métal",
  "Verre",
  "Papier",
  "Carton",
  "Tissu",
  "Caoutchouc",
];
</script>

<template>
  <div>
    <div>Babylink</div>
    <div class="p-3 lg:grid lg:grid-cols-12 lg:gap-4">
      <div class="col-span-2">
        <u-card>
          <div class="flex flex-col gap-4">
            <div>
              <p class="text-sm font-bold text-primary mb-2">Marques</p>
              <UCheckbox
                v-for="brand in brands"
                :id="brand"
                :key="`brand-${brand}`"
                v-model="form.brands"
                :name="brand"
                :label="brand"
                :value="brand"
                class="mb-0"
              />
            </div>

            <UDivider />
            <div>
              <p class="text-sm font-bold text-primary mb-2">
                Taille des couches
              </p>
              <UCheckbox
                v-for="size in sizes"
                :id="size"
                :key="`brand-${size}`"
                v-model="form.sizes"
                :name="size"
                :label="size"
                :value="size"
                class="cursor-pointer"
              />
            </div>

            <UDivider />

            <div>
              <p class="text-sm font-bold text-primary mb-2">
                Lieux de fabrication
              </p>
              <UCheckbox
                v-for="location in productionLocations"
                :id="location"
                :key="`brand-${location}`"
                v-model="form.productionLocations"
                :name="location"
                :label="location"
                :value="location"
              />
            </div>

            <UDivider />

            <div>
              <p class="text-sm font-bold text-primary mb-2">
                Type de matériau non utilisé
              </p>
              <UCheckbox
                v-for="unusedMaterial in unusedMaterials"
                :id="unusedMaterial"
                :key="`brand-${unusedMaterial}`"
                v-model="form.unusedMaterials"
                :name="unusedMaterial"
                :label="unusedMaterial"
                :value="unusedMaterial"
              />
            </div>

            <UDivider />
            <div>
              <p class="text-sm font-bold text-primary mb-2">Matière</p>
              <UCheckbox
                v-for="material in materials"
                :id="material"
                :key="`brand-${material}`"
                v-model="form.materials"
                :name="material"
                :label="material"
                :value="material"
              />
            </div>
          </div>
        </u-card>
        <u-card>
          <div>
            <nuxt-link to="/faq" class="text-sm font-bold text-primary mb-2"
              >FAQ</nuxt-link
            >
          </div>
        </u-card>
      </div>
      <div class="col-span-10">
        <u-card>
          <UTable :rows="resultGetter" :columns="columns" />
        </u-card>
      </div>
    </div>
  </div>
</template>
