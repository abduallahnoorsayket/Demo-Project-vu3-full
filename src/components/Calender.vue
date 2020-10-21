<template>
  <div class="m-auto">
    <h1 class="text-center mb-4 mt-4">Calender</h1>
    <section class="flex">
        <p class="p-2" v-for="day in days" :key="day"> {{day}} </p>
    </section>
  </div>
</template>

<script>
export default {

    data(){
        return{
            days:['sun','mon','tue','wed','thu','fri','sat']
        }

    }

};
</script>

<style>
</style>