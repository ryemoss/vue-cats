<template>
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
</template>

<script>
export default {
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

<style lang="less" scoped>
@accent: aquamarine;
@dark: dimgray;
@black: #222;

h1,h2,h3{
  margin: 12px;
}
h1{
  font-weight: 200;
}
h3{
  color: #555;
  font-weight: 200;
}
ul{
  display: flex;
  flex-direction: column;
  list-style-type: none;
  width: 100%;
  padding: 0;
}
li{
  background-color: @accent;
  text-align: center;
  border-radius: 5px;
  padding: 4px;
  margin: 10px 0;
  min-width: 555px;
}
form{
  text-align: left;
}
input{
  width: 100%;
  margin-bottom: 3px;
}
label{
  font-size: 12px;
}
input[type=submit],
.inputbtn{
  margin-top: 15px;
  width: 50%;
  border: none;
  background: @black;
  color: white;
  font-family: inherit;
}
.banner{
  background-color: @dark;
}
.card-container{
  width: 70%;
  max-width: 720px;
  margin: 20px auto;
  padding: 0 20px;
  box-sizing: border-box;
}
.card-master{
  display: flex;
  position: relative;
  flex-direction: column;
  justify-content: center;
  button{
    position: absolute;
    right: 2px;
    top: 2px;
    color: white;
    font-size: 12px;
    border: 1px solid white;
    border-radius:50%;
    background-color: transparent;
    padding: 2px 5px;
  }
  button:hover{
    color: black;
    border-color: black;
  }
  .imgcontainer{
    margin: 0 30px;
    width: 240px;
    height: 240px;
  }
  img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    border: 2px solid lightgray;
  }
}
.card-details{
  display:flex;
  flex-direction: row;
  background-color: white;
  text-align: left;
  margin: 10px 1px 1px;
  border-radius: 5px;
  padding: 30px;
}
.catinfo{
  margin-left: 20px;
}
.addCatForm{
  padding: 10px 24px 20px;
  background-color: lightgray;
  border-radius: 5px;
  max-width: 400px;
  margin: 0 auto;
}
</style>
