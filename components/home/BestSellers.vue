<template>
  <div class="container">
    <SectionTitle>Best Sellers</SectionTitle>
    <div class="grid cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
      <ProductCard
        v-for="product in products"
        :key="product.title"
        :title="product.title"
        :description="product.description"
        :category="product.category"
        :price="product.price"
        :buttonText="product.buttonText"
        :imageSrc="product.imageSrc"
        :horizontal="false"
      />
    </div>
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
