<template>
  <div>
      <div class="horse">
        <div v-for="(horse,id) in horses" :key="id" class=" animate__animated animate__pulse">
          <img :src="horse" alt="">
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Horse',
  data() {
    return {
      horses: [
        'https://source.unsplash.com/random/200x200?horse',
        'https://source.unsplash.com/random/200x200?horse',
        'https://source.unsplash.com/random/200x200?horse',
        'https://source.unsplash.com/random/200x200?horse',
        'https://source.unsplash.com/random/200x200?horse',
      ]
    }
  }
}
</script>

<style scoped>
.horse{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>