<template>
  <div>
    <h2>About</h2>
    <p>
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Amet ipsa ex
      consequuntur facilis officiis laboriosam in aliquam id aperiam
      reprehenderit?
    </p>
    <p>{{ data }}</p>
  </div>
</template>

<script lang="js" setup>
  const { data} = await useFetch('/api/ninja?name=mario', {
    method: 'post',
    body: { age: 30}
  })
</script>

<style scoped>
h2 {
  margin-bottom: 20px;
  font-size: 36px;
}
p {
  margin: 20px 0;
}
</style>