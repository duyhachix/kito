<template>
	<div id="app">
		<app-header></app-header>
		<app-body></app-body>
	</div>
</template>

<script>
// import components
import AppHeader from './components/AppHeader.vue';
import AppBody from './components/AppBody.vue';

export default {
	name: 'App',
	components: {
		AppHeader,
		AppBody,
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
}
</style>
