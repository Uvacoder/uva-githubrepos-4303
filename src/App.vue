<template>

  <Projects class="pad"></Projects>
  <Input/>
</template>

<script>
import Projects from './components/Projects.vue'
import Input from './components/Input.vue'

export default {
  name: 'App',
  components: {
    Projects,
    Input
  }
}
</script>

<style>
.pad{
  padding: 3.5% 8% 3.5% 8%;
}

</style>
