<template>
    <div @click="itemClick">
        <!--Image-->
        <img src="image">
        <!--Title-->
        <h1>{{ title }}</h1>
        <!--Description-->
        <h2> {{ description }}</h2>
    </div>
</template>

<script>
export default {
    name: 'ListItem',
    props: ['item'],
    data(){
        return {
            image: this.item.image,
            title: this.item.title,
            description: this.item.description,
        }
    },
    methods: {
        itemClick(){
            this.$emit('item-click', this.item)
        }
    }
}
</script>

<style>

</style>