<script setup>
import { reactive, computed, ref } from "vue";

const { data } = await useAsyncData("market", () =>
  $fetch(
    `https://api.dev.inoutdelivery.com.co/v1/products?business=ppc.inoutdelivery.com`
  )
);

const products = data._rawValue;
</script>

<template>
  <div class="emcabezado">
    <h2 >Productos</h2>
  </div>
  <div class="card-container">
    <div v-for="product in products" :key="product" class="card">
      <img :src="product.image.xs" alt="Image 1" />
      <h3 v-text="product.name"></h3>
      <p v-text="product.description"></p>
      <p>${{ product.price }}</p>
    </div>
  </div>
</template>
<style scoped>
.emcabezado{
  text-align: center;
}
.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  width: 90%;
  margin: 50px auto;
}

.card {
  width: 25%;
  background-color: #f2f2f2;
  border-radius: 10px;
  box-shadow: 0 0 10px #ccc;
  padding: 20px;
  text-align: center;
  margin-bottom: 30px;
}

img {
  width: 100%;
  height: 200px;
  border-radius: 10px 10px 0 0;
  object-fit: cover;
}

h3 {
  font-size: 20px;
  font-weight: bold;
  margin: 20px 0;
}

p {
  font-size: 16px;
  line-height: 1.5;
  margin: 0;
}
</style>