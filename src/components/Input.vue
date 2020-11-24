<template>

<div>
<h2>Check you own github repo here</h2>
<div class="input-group mb-3">
  <input type="text" class="form-control" placeholder="Enter username" aria-label="Recipient's username" 
  aria-describedby="basic-addon2"
  v-model="username">
  <div class="input-group-append">
    <button class="btn btn-outline-secondary" type="button" v-on:click="getRepo()">Search</button>
  </div>
</div>
</div>


</template>

<script>

export default {
  name: 'Input',
  data(){
    return {
      username: ""
    };
  },
  methods:{
    getRepo: function(){
      this.$emit('change-repo',this.username);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@media only screen and (min-width: 800px) {
.input-group{
    width: 50%;
    margin: 2% 20% 5% 25%;
}
}

@media only screen and (max-width: 800px) {
.input-group{
    width: 80%;
    margin: 2% 10% 5% 10%;
}
}


h2{
    text-align:center;
    color:red;
}
</style>
