<template>
  <div>
      <table>
          <tr>
              <td><label for="thing">Thing</label></td>
              <td><input type="url" id="thing" v-model="thing"></td>
          </tr>
          <tr>
              <td><label for="amount">Amount</label></td>
              <td><input type="number"></td>
          </tr>
          <tr>
              <td><label for="description">Description</label></td>
              <td><input type="text"></td>
          </tr>
          <tr>
              <td><label for="deadline">Deadline</label></td>
              <td><input type="datetime-local"></td>
          </tr>
          <tr>
              <td></td>
              <td><button type="button" @click="addThing">{{ opText }}</button></td>
          </tr>
      </table>
  </div>
</template>

<script>
export default {
    name: 'OrderForm',
    module: {},
    data(){
      return{

      }
    },
    props: ['selectedItem'],
    methods: {
      addThing(){
        
      }
    },
    computed: {
      opText(){
        if(this.selectedItem === undefined){
          return 'Create Order';
        }else{
          return 'Send Edit';
        }
      }
    }
}
</script>

<style>

</style>