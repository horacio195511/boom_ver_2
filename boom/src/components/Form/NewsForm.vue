<template>
    <div>
        <table>
            <tr>
                <td><label for="title">Title</label></td>
                <td><input id="title" type="text" v-model="title"></td>
            </tr>
            <tr>
                <td><label for="article">Article</label></td>
                <td><input id="article" type="text" v-model="article"></td>
            </tr>
            <tr>
                <td><label for="publishDate">Publish Date</label></td>
                <td><input id="publishDate" type="datetime-local" v-model="publishDate"></td>
            </tr>
            <tr>
                <td></td>
                <td><button type="button" @click="createNews">{{ opText }}</button></td>
            </tr>
        </table>
    </div>
</template>

<script>
export default {
    name: 'NewsForm',
    module: {},
    props: ['selectedItem'],
    methods:{
        createNews(){}
    },
    computed:{
        opText(){
            if(this.selectedItem === undefined){
                return 'Create News';
            }else{
                return 'Send Edit';
            }
        },
    },
    data(){
        return {

        }
    }
}
</script>

<style>

</style>