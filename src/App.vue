<template>
  <div>
    <h1> DC heros :</h1>
    <ul>
    
      <li v-for="(hero,index) in dcHeros "  :key="hero">{{index}}  {{hero.name}}</li>
    </ul>
    <input :[attribute]="newHero">
    <button :disabled="isActive">Add hero</button>
  </div>
</template>

<script>
export default {
  data(){
   
    return{
      attribute: "value",
      isActive: false,
       newHero:"Aqaman mister",
      dcHeros: [
        {name:"superman"},
        {name:"flash"},
        {name:"ironman"},
        {name: "wonderWomen"}
      ]
              
    }
  }

}
</script>

<style>

</style>