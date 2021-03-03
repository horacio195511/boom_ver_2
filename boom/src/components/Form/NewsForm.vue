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
    name: 'CreateNews',
    props: ['selectedItem'],
    methods:{
        createNews(){
            if(this.selectedItem === undefined){
                // for creation
                const formdata = new FormData();
                formdata.append('title', this.title);
                formdata.append('article', this.article);
                formdata.append('author', 'test');
                formdata.append('create', new Date());
                formdata.append('publish', this.publishDate);
                fetch('http://localhost:7000/createNEWS', {
                    method: 'POST',
                    mode: 'cors',
                    credentials: 'same-origin',
                    body: formdata,
                }).then((response) => {
                    if(!response.ok){
                        throw new Error('--server error--');
                    }else{
                        return response.json();
                    }
                }).then((jsonResponse) => {
                    if(jsonResponse.result === 'success'){
                        console.log(jsonResponse.result);
                    }
                });
            } else{
                // for editting
                const formdata = new FormData();
                formdata.append('id', this.selectedItem.id);
                formdata.append('title', this.title);
                formdata.append('article', this.article);
                formdata.append('author', 'test');
                formdata.append('create', new Date());
                formdata.append('publish', this.publishDate);
                fetch('http://localhost:7000/editNEWS', {
                    method: 'POST',
                    mode: 'cors',
                    credentials: 'same-origin',
                    body: formdata,
                }).then((response) => {
                    if(!response.ok){
                        throw new Error('--server error--');
                    }else{
                        return response.json();
                    }
                }).then((jsonResponse) => {
                    if(jsonResponse.result === 'success'){
                        console.log(jsonResponse.result);
                    }
                });

            }
        }
    },
    computed:{
        opText(){
            if(this.selectedItem === undefined){
                return 'Create News';
            }else{
                return 'Send Edit';
            }
        }
    }
}
</script>

<style>

</style>