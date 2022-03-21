<template>
  <div class="home">{{ commits }}</div>
  <li v-for="item in commits" v-bind:key="item.sha">Commit{{ item.sha }}</li>
    Commit <router-link to="/about">{{ imem.sha }}</router-link>
</template>

<script>
let ovjekt = {
name: "HomeView",
data: function() {
  return{
    commits: [],

  };

},
async mounted(){
  let podatci = await fetch('https://api.github.com/repos/vuejs/vue/commits');
  console.log(podatci);

  let rezultati = await podatci.json();
console.log(rezultati);

for(let item of rezultati){
console.log(rezultati.sha);
}


this.commits = rezultati;
}



}

</script>
