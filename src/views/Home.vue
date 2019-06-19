<template>
 <!--  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div> -->
<div>
 <div class="ava">
      <img src="https://avatars0.githubusercontent.com/u/44156942?s=460&v=4">
    </div>
    <h1><a href="https://github.com/Garrusir">GitHub</a></h1>
</div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>
<style >
	.links {
		display: flex;
		flex-flow: column nowrap;
		margin: 15px;
	}
	.links a {
		margin: 5px ;
	}

  .ava img {
  margin: 10px auto;
  border-radius: 50%;
  max-width: 200px;
  box-shadow: 0 2px 2px 2px rgba(0,0,0, .25);
  }
</style>