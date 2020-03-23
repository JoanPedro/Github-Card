<template>
	<div class="ui card">
      <div class="image">
        <img :src="user.avatar_url">
      </div>
      <div class="content">
        <a :href="`https://github.com/${username}`" class="header">{{user.name}}</a>
        <div class="meta">
          <span class="date">Joined in {{user.created_at}}</span>
        </div>
        <div class="description">
          {{user.bio}}
        </div>
      </div>
      <div class="extra content">
        <a :href="`https://github.com/${username}?tab=followers`">
          <i class="user icon"></i>
          {{user.followers}} Friends
        </a>
      </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
	name: "GitHubCard",
	props: {
		username: {
			type: String,
			required: true
		}
	},
	components: '',
	computed: '',
	data: function() {
		return {
			user: {}
		}
	},
	methods: {

	},
	created() {
		axios.get(`https://api.github.com/users/${this.username}`)
			.then(res => {
				this.user = res.data
			})
			.catch(e => {
				throw(e)
			})
	}
}
</script>

<style>
.shopping-list {
	background-color: white;
	box-shadow: 2px 2px 3px 3px rgba(0, 0, 0, 0.2);
	padding: 20px;
	margin: 50px;
}

</style>