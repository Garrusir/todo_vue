<template>
 <!--  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div> -->

  <div class="main">
  	<h1>HTML Academy</h1>
  	<div class="links">
  		<a href="https://htmlacademy.ru/courses/50" target="_blank">Мастерская: создаём меню</a>
  		<a href="https://htmlacademy.ru/courses/55" target="_blank">Мастерская: декоративные элементы</a>
  	</div>
  	<div class="links">
  		<a href="https://htmlacademy.ru/courses/130" target="_blank">Знакомство с SVG</a>
  		<a href="https://htmlacademy.ru/courses/187" target="_blank">Оформление SVG-фигур</a>
  		<a href="https://htmlacademy.ru/courses/259" target="_blank">Размеры SVG</a>
  	</div>
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

</style>