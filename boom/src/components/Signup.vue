<template>
  <table>
      <tr>
          <td><label for="privateKey">Private Key</label></td>
          <td><input id="privateKey" type="text"></td>
      </tr>
      <tr>
          <td><label for="position">Position</label></td>
          <td><input id="position" type="text"></td>
      </tr>
      <tr>
          <td></td>
          <td><button type="button" @click="signup">Signup</button></td>
      </tr>
  </table>
</template>

<script>
export default {
    name: 'Signup',
    methods:{
        genKey(){
            console.log(window.ethereum);
        },
        signup(){
            // set up the position of certain user
            // the operation to register as site manager should
            // always authorized by me.
            
        }
    }
}
</script>

<style>

</style>