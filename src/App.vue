<template>
  <div>
    <!-- start food  -->
    <div class="food">
      <div v-for="(food,id) in foods" :key="id">
      {{food}}
      </div>
    </div>
    <!-- end food  -->
    <!-- start mygallery  -->
    <div class="mygallery">
      <div v-for="gallerys in gallery" :key="gallerys">
        <img :src="gallerys" alt="">
      </div>
    </div>
    <!-- end mygallery  -->
    <!-- start animals  -->
    <div class="animals">
      <button @click="animals='Ant'">Ant</button>
      <button @click="animals='Fox'">Fox</button>
      <button @click="animals='Horse'">Horse</button>
      <button @click="animals='Spidder'">Spidder</button>
    </div>
    <component :is="animals"></component>
    <!-- end animals  -->
    <!-- start animalbooks  -->
    <div class="animalbooks">
      <div v-for="book in books" :key="book.id" class="animate__animated animate__swing">
        <h3>{{book.name}}</h3>
        <img :src="book.img" alt="">
        <p>{{book.buy}}</p>
      </div>
    </div>
    <!-- end animalbooks  -->
    <!-- start animalcount  -->
    <div class="animalcount">
      <Animalcount animalname="Cat" :animalimage="animalCount[0]" country="Bangladesh" :numberofAnimal="200"/>
      <Animalcount animalname="Ant" :animalimage="animalCount[1]" country="America" :numberofAnimal="200"/>
      <Animalcount animalname="Tiger"  :animalimage="animalCount[2]" country="England" :numberofAnimal="200"/>
      <Animalcount animalname="Fox" :animalimage="animalCount[3]" country="Turky" :numberofAnimal="200"/>
    </div>
    <!-- end animalcount  -->
    <!-- start forst  -->
    <div>
      <Forest id="forest">
        <template v-slot:aki>
          <div v-bind="$attrs">
            People living in the countryside and others from yogic or tribal traditions people look at forests with respect, seeing them as ancient, sacred and mysterious.  Others support themselves on the laws of science, recognizing forests as incredible biodiversity hotspots and the best “technology” we have to fight climate change. Yet, in the stressed and sometimes far way urban life it’s easy to forget about forests and how crucial they are for the balance of the Earth and for our long term survival.
          </div>
        </template>
      </Forest>
    </div>
    <!-- end forst  -->
    <!-- start Forestnonpros  -->
    <Forestnonprops />
    <!-- end Forestnonpros  -->
    <!-- start percent of animal -->
    <div>
      <div v-if="animalPercent>=25">
        <p>Animal percent 25 in this country, which is good.</p>
      </div>
      <div v-else>
        <p>Animal less then 25 percent in this country, which is bad.</p>
      </div>
    </div>
    <!-- end percent of animal -->
    <!-- start toggle  -->
    <div>
      <button @click="toggleAlert()">Toggle</button>
    </div>
    <!-- end toggle  -->
    <!-- start counter  -->
    <div class="counter">
      <input type="text" v-model="counter">
      <div class="mybtn">
        <button @click="increment(1)">Increment 1</button>
        <button @click="decrement(1)">Decrement 1</button>
        <button @click="increment(5)">Increment 5</button>
        <button @click="decrement(5)">Decrement 5</button>
      </div>
    </div>
    <!-- end counter  -->
    <!-- start toggle text  -->
    <div>
      <div class="mytext" :class="{mybg:published}">
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Perferendis fugiat minima, sed perspiciatis culpa eius consequatur unde vel tempore inventore dolor sequi doloremque officiis modi quae, maxime maiores vitae commodi?
      </div>
      <button @click="bgToggle()">Toggle Background</button>
    </div>
    <!-- end toggle text  -->
    <!-- start signUp  -->
    <SignUp />
    <!-- end signUp  -->
    <!-- start signIn  -->
    <!-- end signIn  -->

  </div>
</template>

<script>
import Ant from './components/Ant.vue';
import Fox from './components/Fox.vue';
import Horse from './components/Horse.vue';
import Spidder from './components/Spidder.vue';
import Animalcount from './components/Animalcount.vue';
import Forest from './components/Forest.vue';
import Forestnonprops from './components/Forestnonprops.vue';
import SignUp from './components/SignUp.vue';
import {animalbooks} from './mixin';
export default {
  name: 'App',
  components: {
    Ant,
    Fox,
    Horse,
    Spidder,
    Animalcount,
    Forest,
    Forestnonprops,
    SignUp
  },
  data() {
    return {
      foods: ['banana','guava','watermelon','plum','mango','coconut'],
      gallery: [
        'https://source.unsplash.com/random/200x200?nature',
        'https://source.unsplash.com/random/200x200?man',
        'https://source.unsplash.com/random/200x200?girl',
        'https://source.unsplash.com/random/200x200?computer',
      ],
      animalCount: [
        'https://source.unsplash.com/random/200x200?cat',
        'https://source.unsplash.com/random/200x200?ant',
        'https://source.unsplash.com/random/200x200?tiger',
        'https://source.unsplash.com/random/200x200?fox',
      ],
      animals: 'Ant',
      myimage: 'hello',
      animalPercent: 24,
      published: false,
      counter: 1
    }
  },
  methods: {
    toggleAlert(){
      alert('Welcome to simple App')
    },
    increment(num){
      return this.counter += num;
    },
    decrement(num){
      return this.counter -= num;
    },
    bgToggle() {
      this.published = !this.published;
    }
  },
  computed: {
    
  },
  mixins: [animalbooks]
}
</script>

<style scoped>
/* start food */
.food{
  display: flex;
  flex-wrap: wrap;
  border: 1px solid black;
  padding: 10px;
  justify-content: space-around;
}
/* end food */
/* start mygallery  */
.mygallery{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
.animals{
  text-align: center;
  margin: 10px;
}
.animals button{
  padding: 20px;
  border: none;
}
/* end mygallery  */
/* start animalbooks  */
.animalbooks{
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  text-align: center;
}
.animalbooks h3,p{
  border: 1px solid black;
  padding: 10px;
}
.animalbooks h3:hover,p:hover{
  background: #ddd;
}
/* end animalbooks  */
/* start animalcount  */
.animalcount{
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  background: #ddd;
}
/* end animalcount  */
/* start forest  */
/* end forest  */
/* start Forestpros  */
/* end Forestpros  */
/* start percent of animal */
/* end percent of animal */
/* start toggle  */
/* end toggle  */
/* start counter  */
.counter{
  text-align: center;
}
.counter .mybtn{
  display: flex;
  justify-content: center;
}
/* end counter  */
/* start toggle text  */
.mytext{
  color: green;
}
.mybg{
  background: #ddd;
}
/* end toggle text  */
</style>