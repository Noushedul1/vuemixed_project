<template>
  <div>
      <div class="fox">
        <div v-for="(fox,id) in foxs" :key="id" class="animate__animated animate__pulse">
          <img :src="fox" alt="">
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Fox',
  data() {
    return {
      foxs: [
        'https://source.unsplash.com/random/200x200?fox',
        'https://source.unsplash.com/random/200x200?fox',
        'https://source.unsplash.com/random/200x200?fox',
        'https://source.unsplash.com/random/200x200?fox',
        'https://source.unsplash.com/random/200x200?fox',
      ]
    }
  }
}
</script>

<style scoped>
.fox{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>