<template>
   <div class="container ">
  <div class="row">
  <div class="col-md-12 ">
    
    <div class="mt-4 ml-4">
    <h1 class=" header  mb-4"> DC heros  {{herosCount}} </h1>
    <ul>
    
      <li class="" v-for="(hero,index) in dcHeros "  :key="hero.name">
        <p>{{hero.name}}  <button v-on:click="remove(index)">x</button></p> 
        
        </li>
    </ul>
  <div class="mb-4">
    <form @submit.prevent="addHero">
     
      <input v-model.trim="newHero" placeholder="Enter your hero ">
      <button type="submit">Add hero</button> <br>
      
    </form>
    <small> Total hereos in the list {{herosCount}}</small>
  </div>

  </div>
  </div>
</div>
</div>
</template>

<script>
export default {
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
   computed:{
    herosCount(){
      return this.dcHeros.length;
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