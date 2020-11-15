<template>

  <Projects class="pad" v-bind:repos="repos"></Projects>
  <Input v-on:change-repo="getrep($event)"/>
</template>

<script>
import Projects from './components/Projects.vue'
import Input from './components/Input.vue'

export default {
  name: 'App',
  data(){
    return{
      username: "Kash15if",
      repos: {}
    }
  },
  components: {
    Projects,
    Input
  },
  methods: {

      getrep: async function(newRepo){
        this.username = newRepo;
        const url = "https://api.github.com/users/" + this.username + "/repos"
        const response = await fetch(url)
      
        this.repos = await response.json();
        await console.log(this.repos);

      }
  },
  async created(){
      
      const url = "https://api.github.com/users/" + this.username + "/repos"
      const response = await fetch(url)
      
      this.repos = await response.json();
      await console.log(this.repos);

  }
}
</script>

<style>
.pad{
  padding: 3.5% 8% 3.5% 8%;
}
    .btn{
        background-color: rgb(59, 17, 128);
        color: white;
        width: auto;
    }

</style>
