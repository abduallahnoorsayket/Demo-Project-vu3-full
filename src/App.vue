<template>
<div class="text-center">
    <h1> DC heros Members {{herosCount}} </h1>
    <ul>
    
      <li v-for="(hero,index) in dcHeros "  :key="hero.name">
        <p>{{hero.name}}  <button v-on:click="remove(index)">x</button></p> 
        
        </li>
    </ul>
  <form @submit.prevent="addHero">
     
      <input v-model.trim="newHero" placeholder="Enter your hero ">
      <button type="submit">Add hero</button> <br>
      
  </form>
  <small> Total hereos in the list {{herosCount}}</small>
  </div>
 
</template>

<script> 
export default {
  computed:{
    herosCount(){
      return this.dcHeros.length;
    }
      
  },
  data(){
   
    return{
      
      isActive: false,
       newHero:"",
      dcHeros: [
        {name:"superman"},
        {name:"flash"},
        {name:"ironman"},
        {name: "wonderWomen"}
      ]
              
    }
  },
  methods:{
    addHero(){
    if(this.newHero != ''){
            this.dcHeros.push({name:this .newHero});
          this.newHero='';
    }
    },
    remove(index){
       this.dcHeros  = this.dcHeros.filter((hero,i) => i != index);
    }

  }

}
</script>

<style>

</style>