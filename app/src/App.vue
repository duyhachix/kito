<template>
	<div id="app">
		<app-header></app-header>
		<app-body></app-body>
		<app-footer></app-footer>
	</div>
</template>

<script>
// import components
import AppHeader from './components/AppHeader.vue';
import AppBody from './components/AppBody.vue';
import AppFooter from './components/AppFooter.vue';

export default {
	name: 'App',
	components: {
		AppHeader,
		AppBody,
		AppFooter,
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
