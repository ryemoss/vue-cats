<template>
  <div>
    <button @click="addCat()">ADD CAT</button>
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
      ]
    }
  },
  methods: {
    addCat(){

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
  margin: 10px;
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
</style>
