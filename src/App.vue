<template>
	<div class="app">
		<post-form
			@create="createPost"
		
		/>
		<posts-list 
			:posts="posts"
		/>
	</div>
</template>
<script>
import PostForm from '@/components/PostForm.vue';
import PostsList from '@/components/PostsList.vue';

export default {
	components: {
		PostsList, PostForm
	},
	data() {
		return {
			posts: [
				{id: 1, title: 'JavaScript _1', body: 'Описание поста 1'},
				{id: 2, title: 'JavaScript _2', body: 'Описание поста 2'},
				{id: 3, title: 'JavaScript _3', body: 'Описание поста 3'},
			]
		}
	},
	methods: {
		createPost(post) {
			this.posts.push(post);
		},
		inputTitle(event) {
			this.title = event.target.value;
		},
		inputBody(event) {
			this.body = event.target.value;
		},
	}
}
</script>
<style>
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
.app {
	padding: 20px;
}

</style>
