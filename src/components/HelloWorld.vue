<template>
 <div class="row">

      <div class="col-md-3 " v-for="(repo,index) in repos" :key="index">
      <a v-bind:href=repo.html_url>
        <div class="card" >
          <div class="card-body">
            <h5 class="card-title" >{{repo.name}}</h5>
            <p class="card-text">{{repo.description}}</p>
            <h6 class="card-subtitle mb-2 text-muted">Language: {{repo.language}}</h6>
            <p class="card-text">stars {{repo.forks_count}}   <span class="float-right">pull req {{" " + repo.forks_count}}</span></p>
            
            <div class="text-center">
              <a v-bind:href=repo.homepage class="btn btn-primary" style="width: 60%; margin-top: 20px;">website</a>
            </div>
            
          </div>
        </div>
        </a>
        
      </div>


    </div>

</template>

<script>

export default {
  name: 'HelloWorld',
  data(){
    return {
      repos: {}
    };
  },
  async created(){
      
      const response = await fetch('https://api.github.com/users/Kash15if/repos')
      
      this.repos = await response.json();
      await console.log(this.repos);

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .btn{
        background-color: rgb(59, 17, 128);
        color: white;
        width: auto;
        
    }
    a{
      text-decoration: none;
      color:#263238;
    }
    .card{
      margin-top: 25px;
    }
</style>
