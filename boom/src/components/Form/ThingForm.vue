<template>
  <div>
      <table>
          <tr>
              <td><label for="name">Name</label></td>
              <td><input id="name" type="text"></td>
          </tr>
          <tr>
              <td><label for="description">Description</label></td>
              <td><input id="description" type="text"></td>
          </tr>
          <tr>
              <td><label for="price">Price</label></td>
              <td><input id="price" type="number"></td>
          </tr>
          <tr>
              <td><label for="file">File</label></td>
              <td><input id="file" type="file"></td>
          </tr>
          <tr>
              <td></td>
              <td><button type="button" @click="createThing">{{ opText }}</button></td>
          </tr>
      </table>
  </div>
</template>

<script>
export default {
    name: 'ThingForm',
    module: {},
    data(){
        return{

        }
    },
    props: ['selectedItem'],
    methods: {
        createThing(){}
    },
    computed: {
        opText(){
            if(this.selectedItem === undefined){
                return 'Create Thing';
            }else{
                return 'Send Edit';
            }
        }
    }
}
</script>

<style>

</style>