<template>
  <div class="py-8 container">
    <div class="flex flex-col gap-4 md:flex-row">
      <div class="flex flex-col gap-4 md:max-w-[700px]">
        <h1 class="text-4xl md:text-6xl lg:text-8xl">Breath Natureal</h1>
        <p class="text-lg font-thin lg:text-2xl">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua.
        </p>
        <UiButton>Explore</UiButton>
      </div>
      <ProductCarousel :products="products" />
    </div>
    <NuxtImg
      src="/images/hero.png"
      alt="Hero image"
      width="600"
      class="absolute left-1/2 -translate-x-1/2 top-72 -z-10"
    />
    <SectionTitle>Featured Plants</SectionTitle>
    <ProductCard
      v-for="product in products"
      :key="product.title"
      :title="product.title"
      :description="product.description"
      :category="product.category"
      :price="product.price"
      :buttonText="product.buttonText"
      :imageSrc="product.imageSrc"
      :horizontal="true"
    />
  </div>
</template>

<script setup lang="ts">
const products = [
  {
    title: "Calathea Plant",
    description: "A beautiful houseplant with striking green and white leaves.",
    category: "Indoor Plant",
    price: "45.99",
    buttonText: "Buy now",
    imageSrc: "/images/plant-1.png",
  },
  {
    title: "Snake Plant",
    description:
      "Low-maintenance and perfect for improving indoor air quality.",
    category: "Succulent",
    price: "29.99",
    buttonText: "Add to cart",
    imageSrc: "/images/plant-1.png",
  },
  {
    title: "Fiddle Leaf Fig",
    description:
      "A trendy plant with large, glossy leaves that thrive in bright light.",
    category: "Decorative Plant",
    price: "89.99",
    buttonText: "Shop now",
    imageSrc: "/images/plant-1.png",
  },
  {
    title: "Peace Lily",
    description:
      "An elegant flowering plant that purifies the air in your home.",
    category: "Flowering Plant",
    price: "34.99",
    buttonText: "Order now",
    imageSrc: "/images/plant-1.png",
  },
  {
    title: "Aloe Vera",
    description: "A multipurpose succulent known for its soothing properties.",
    category: "Medicinal Plant",
    price: "19.99",
    buttonText: "Get one",
    imageSrc: "/images/plant-1.png",
  },
];
</script>
