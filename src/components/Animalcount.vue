<template>
  <div>
      <p>{{animalname}}</p>
      <img :src="animalimage" alt="">
      <p>{{country}}</p>
      <p>{{numberofAnimal}}</p>
  </div>
</template>

<script>
export default {
    name: 'Animalcount',
    props: {
        animalname: String,
        country: String,
        numberofAnimal: Number,
        animalimage: {
            type: String,
            required: true
        }
    }
}
</script>

<style>

</style>