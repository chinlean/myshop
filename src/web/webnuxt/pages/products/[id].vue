<template>
  <div>
  <Head>
    <Title> Nuxt Dojo | {{ product.title }}</Title>
    <Meta name="description" :content="product.description"/>
  </Head>
    <ProductDetails :product="product"/>
  </div>
</template>

<script setup lang="js">
 
 const {id } = useRoute().params;
 const uri = 'http://fakestoreapi.com/products/' + id

 const { data : product} = await useFetch(uri)

  if(!product.value) {
    throw createError({statusCode : 404, message : 'Product not found'})
  }
 console.log(product)


 definePageMeta({
    layout: 'products'
  })


</script>

<style scoped>
</style>