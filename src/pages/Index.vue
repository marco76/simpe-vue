<template>
  <q-page>
    <!--<img alt="Quasar logo" src="~assets/running.svg" style="width: 300px; height: 300px">-->

<div class="catalog-title">
Catalog
</div>
<div id="container" class="flex flex-center">
<div v-for="product in products" :key="product">
  <!-- <product-data :product="product"></product-data>-->
  <q-card style="width: 250px; margin: 20px">
  <q-card-title>
    {{product.name}}
    <span slot="subtitle">
      <router-link to="/company">{{product.company}}</router-link></span>
  </q-card-title>
  <q-card-separator />
  <q-card-main>
    {{product.description}}
  </q-card-main>
  <q-card-separator />
  <q-card-media style="width: 250px; height: 250px">
    <img v-bind:src="product.image"/>
</q-card-media>
  <q-card-separator />
    <div style="margin-top: 10px; margin-left: 10px">
       <p class="text-faded">Number: {{product.number}}</p>
    </div>
  <q-card-separator />
  <q-card-actions>
    <q-btn flat round dense icon="add_shopping_cart" />
    <q-btn flat label="Info" />
    <q-btn flat label="See variations" />
    <!-- <q-btn flat color="primary" label="Reserve" /> -->
  </q-card-actions>
</q-card>
</div>
</div>
<!--
<input v-model="message" placeholder="edit me">
<p>Message is: {{ model }}</p>
for {{ company.name }}
-->
</q-page>
 </template>

<style lang="css">
@import '/src/statics/css/main.css';
.catalog-title {
    text-align: center;
    margin-top: 10px;
    font-size: 3em;
    color: #a1a1a1;
}
</style>

<script> // import ProductData from '../components/ProductData.vue'

export default {
  name: 'PageIndex',
  data: function () {
    return {
      products: [
        {
          name: 'product1',
          number: '0012312',
          image: 'https://www.bestfunnies.com/wp-content/uploads/2015/06/Funny-Shoe-Pictures-2.jpg',
          description: 'Beautiful shoes build with solid stones',
          company: 'Mike Shoes',
          implementations: {
            lederstarke: [0.9, 1.0, 1.4]
          }
        },
        {
          name: 'product2',
          company: 'Pandidas Sport',
          image: 'https://www.bestfunnies.com/wp-content/uploads/2015/06/Funny-Shoe-Pictures-4.jpg',
          description: 'Ideal for the raining days',
          number: '0123',
          implementations: {
            lederstarke: [1.0, 1.2]
          }
        }
      ]
    }
  }
  // components: { 'product-data': ProductData }
}
</script>
