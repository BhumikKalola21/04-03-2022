<template>
  <section class="container">
    <h2>{{ username }}</h2>
    <h2>{{ age }}</h2>
    <button @click="version">change the version</button>
    <div>
    <input type="text" placeholder="firstname of user" v-model="firstname">
    <input type="text" placeholder="lastname of user" v-model="lastname">
    </div>
  </section>
</template>

<script>
import { ref,computed,watch } from 'vue';
export default {
  setup(){
    // const uName  = ref('Bhumik');
    const uAge = ref(21);
    const firstname = ref('');
    const lastname = ref('');

    const uName = computed(function(){
      return firstname.value + ' ' +lastname.value
      
    });

    watch(uAge,function(newvalue,oldvalue){
      alert('new value:'+newvalue),
      alert('old value:'+oldvalue)
    })

    function agechange(){
      uAge.value = 22;
    }


   return {username:uName,age:uAge,version:agechange,firstname,lastname}
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
</style>
