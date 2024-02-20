<template>
    <form @submit.prevent>
        <h4>Создание поста</h4>
        <!-- @input="post.title = $event.target.value"
        :value="post.title"  -->
        <!-- v-model="post.title" -->
        <my-input 
            v-model:valueX="post.title"
            type="text" 
            placeholder="Название"
        />
        <!-- @input="post.body = $event.target.value"
        :value="post.body"  -->
        <!-- v-model="post.body" -->
        <my-input 
            v-model:valueX="post.body"
            type="text" 
            placeholder="Описание"
        />
        <my-button
            @click="createPost"
        >
            Создать
        </my-button>
    </form>
</template>

<script>
export default {
        data() {
            return {
                post: {
                    title: '',
                    body: '',
                }
            }
        },
        methods: {
            createPost() {
                if (!this.post.title || !this.post.body) {
                    return
                }
                const newPost = {
                    id: Date.now(),
                    title: this.post.title,
                    body: this.post.body,
                };
                // this.post.title = '';
                // this.post.body = '';
                this.$emit('create', this.post)
                this.post = {
                    title:'',
                    body:''
                }
                // this.posts.push(newPost);
            },
        }
    }
</script>

<style scoped>

/* .input {
	border: 2px solid teal;
	padding: 10px 15px;
	margin: 0 20px 20px 20px;
} */
form {
	display: flex;
	flex-direction: column;
}
form h4 {
 margin-bottom: 10px;
}
</style>