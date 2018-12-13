<template>
  <div>
    <app-header></app-header>
    <div class="card-container">
      <ul>
        <li v-for="cat in cats">
          <div class="card-master" v-on:click="cat.show = !cat.show">
            <h2>{{ cat.name }}</h2>
            <div class="card-details" v-show="cat.show">
              <div class="imgcontainer">
                <img v-bind:src="'/src/assets/' + cat.pic" width=240px height=240px />
              </div>
              <div class="catinfo">
                <h3>Breed: {{ cat.breed }}</h3>
                <h3>Gender: {{ cat.gender }}</h3>
                <h3>Age: {{ cat.age }}</h3>
              </div>
            </div>
            <div>
              <button @click="removeCat(cat)">X</button>
            </div>
          </div>
        </li>
      </ul>
      <div>
        <button class="inputbtn" @click="addCat()" v-show="!addingCat">ADD CAT</button>
      </div>
      <div class="addCatForm" v-show="addingCat">
        <form>
          <label>Name</label>
          <input type="text" v-model="addedCat.name"/>
          <label>Breed</label>
          <input type="text" v-model="addedCat.breed"/>
          <label>Gender</label>
          <input type="text" v-model="addedCat.gender" list="genders"/>
          <datalist id="genders">
            <option value="Male"></option>
            <option value="Female"></option>
          </datalist>
          <label>Age</label>
          <input type="number"/>
          <!--<input type="submit" value="SUBMIT"/>-->
        </form>
        <button class="inputbtn" @click="submitCat()">SUBMIT</button>
      </div>
    </div>
  </div>
</template>

<script>
import Footer from './Footer.vue';
import Header from './Header.vue';

export default {
  components:{
    'app-header': Header,
    'app-footer': Footer,
  },
  data () {
    return {
      cats: [
        {name: 'Luna', breed: 'Long Hair', gender: 'male', age: '5 years', pic: 'cat1.jpg', show: false},
        {name: 'Meteor', breed: 'Long Hair', gender: 'female', age: '3 years', pic: 'blankcat.png', show: false},
        {name: 'Jax', breed: 'Hairless', gender: 'male', age: '8 months', pic: 'blankcat.png', show: false},
        {name: 'Moose', breed: 'Calico', gender: 'female', age: '9 years', pic: 'blankcat.png', show: false}
      ],
      addingCat: false,
      addedCat: {name: '', breed: '', gender: '',  age: '', pic:'', show: true}
    }
  },
  methods: {
    removeCat(cat){
      var index = this.cats.indexOf(cat);
      if (index > -1) {
        this.cats.splice(index, 1);
      }
    },
    addCat(){
      this.addingCat = !this.addingCat;
    },
    submitCat(){
      if (this.addedCat.pic === '')
        this.addedCat.pic = 'blankcat.png';
      this.cats.push(this.addedCat);
      this.addCat();
    }
  }
}
</script>
