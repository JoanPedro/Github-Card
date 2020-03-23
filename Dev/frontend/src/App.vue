<template>
	<div id="app" class="ui container">
		<h1> GitHub Profiles </h1>
		<div class="ui cards">
				<GitHubCard	v-for="username in usernames" v-bind:key="username" :username="username" />
		</div>
	</div>
</template>

<script>
import GitHubCard from './components/GitHubCard'
export default {
	name: "App",
	components: {GitHubCard},
	computed: '',
	data: function() {
		return {
			usernames: ['JoanPedro', 'bahia-rafael', 'sdras', 'akryum']
		}
	},
	methods: {
	},
	created() {
	}
}
</script>

<style>
body { 
	background-color: turquoise;
}

</style>