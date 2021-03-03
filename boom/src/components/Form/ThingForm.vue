<template>
  <div>
      <table>
          <tr>
              <td><label for="name"></label></td>
              <td><input id="name" type="text"></td>
          </tr>
          <tr>
              <td><label for="description"></label></td>
              <td><input id="description" type="text"></td>
          </tr>
          <tr>
              <td><label for="price"></label></td>
              <td><input id="price" type="number"></td>
          </tr>
          <tr>
              <td><label for="file"></label></td>
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
    name: 'CreateThing',
    props: ['selectedItem'],
    methods: {
        createThing(){
            
        }
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