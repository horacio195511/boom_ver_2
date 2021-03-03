<template>
    <div>
        <h1>{{ title }}</h1>
        <h2>{{ article }}</h2>
    </div>
</template>

<script>
// this view is used to show the NEWS
export default {
    name: 'NewsFrame',
    props:['news'],
    data(){
        return {
            title: this.news.title,
            article: this.news.article,
        }
    }
}
</script>

<style>

</style>