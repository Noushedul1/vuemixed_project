<template>
  <div>
      <div class="ant">
        <div v-for="(ant,id) in ants" :key="id" class="animate__animated animate__pulse">
          <img :src="ant" alt="">
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Ant',
  data() {
    return {
      ants: [
        'https://source.unsplash.com/random/200x200?ant',
        'https://source.unsplash.com/random/200x200?ant',
        'https://source.unsplash.com/random/200x200?ant',
        'https://source.unsplash.com/random/200x200?ant',
        'https://source.unsplash.com/random/200x200?ant',
      ]
    }
  }
}
</script>

<style scoped>
.ant{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>