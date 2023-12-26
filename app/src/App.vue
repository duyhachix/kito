<template>
	<div id="app" @scroll="handleScroll">
		<app-header></app-header>
		<app-body></app-body>
		<app-footer></app-footer>
		<div class="top-btn" v-if="toTopisShow" @click="scrollToTop">
			<font-awesome-icon :icon="['fas', 'circle-up']" style="color: #ee80a0" size="2xl" />
		</div>
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
	data() {
		return {
			toTopisShow: false,
		};
	},
	created() {
		window.addEventListener('scroll', this.handleScroll);
	},
	methods: {
		scrollToTop() {
			window.scrollTo({ top: 0, behavior: 'smooth' });
		},
		handleScroll() {
			// this.$refs.audio.play();
			this.toTopisShow = window.scrollY > 600;
		},
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
	position: relative;
}
.top-btn {
	position: fixed;
	bottom: 20px;
	right: 20px;
}
</style>
