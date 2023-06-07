<template>
    <form @submit.prevent="createPost">
        <h4>Создание поста</h4>
        <my-input type="text" v-model="post.title" placeholder="Название поста"></my-input>
        <my-input type="text" v-model="post.body" placeholder="Описание поста"></my-input>
        <my-button type="submit" class="btn" style="align-self: flex-end; margin-top: 10px;">Создать</my-button>
    </form>
</template>
<script>
export default {
    data(){
        return{
            post: {
                title: '',
                body: ''
            }
        }
    },
    methods: {
        createPost(){
            this.post.id = Date.now()
            this.$emit('create', this.post)
            this.post = {
                title: '',
                body: ''
            }
        }
    }
}
</script>
<style scoped>
    form{
        display: flex;
        flex-direction: column;
    }
</style>