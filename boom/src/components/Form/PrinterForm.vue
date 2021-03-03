<template>
  <div>
      <table>
          <tr>
              <td><label for="name">Name</label></td>
              <td><input id="name" type="text"></td>
          </tr>
          <tr>
              <td><label for="company">Company</label></td>
              <td><input id="company" type="text"></td>
          </tr>
          <tr>
              <td><label for="model">Model</label></td>
              <td><input id="model" type="text"></td>
          </tr>
          <tr>
              <td><label for="description">Description</label></td>
              <td><input id="description" type="text"></td>
          </tr>
          <tr>
              <td><label for="location">Location</label></td>
              <td><input id="location" type="text"></td>
          </tr>
          <tr>
              <td></td>
              <td><button type="button" @click="createPrinter">{{ opText }}</button></td>
          </tr>
      </table>
  </div>
</template>

<script>
export default {
    name: 'CreatePrinter',
    props: ['selectedItem'],
    methods: {
        createPrinter(){

        }
    },
    computed: {
        opText(){
            if(this.selectedItem === undefined){
                return 'Create Printer';
            }else{
                return 'Send Edit';
            }
        }
    }
}
</script>

<style>

</style>