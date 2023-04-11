<template>
   <div>
      <ProductDetails :product="product" />
   </div>
</template>

<script setup>
   const { id } = useRoute().params

   const uri = 'https://fakestoreapi.com/products/' + id
   // As a 2nd argument, the options object '{ key: id }' is passed so that the route param changes properly.
   const { data: product } = await useFetch(uri, { key: id })

   definePageMeta({
      layout: 'products'
   })
</script>

<style scoped>

</style>