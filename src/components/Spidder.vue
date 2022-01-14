<template>
  <div>
      <div class="spider">
        <div v-for="(spider,id) in spiders" :key="id" class="animate__animated animate__pulse">
          <img :src="spider" alt="">
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Spider',
  data() {
    return {
      spiders: [
        'https://source.unsplash.com/random/200x200?spider',
        'https://source.unsplash.com/random/200x200?spider',
        'https://source.unsplash.com/random/200x200?spider',
        'https://source.unsplash.com/random/200x200?spider',
        'https://source.unsplash.com/random/200x200?spider',
      ]
    }
  }
}
</script>

<style scoped>
.spider{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>