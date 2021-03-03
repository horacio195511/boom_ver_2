<template>
  <div>
      <table>
          <tr>
              <td><label for="privateKey">Private Key</label></td>
              <td><input type="text" placeholder="Enter Ethereum Private Key"></td>
          </tr>
          <tr>
              <td><button type="button" @click="userSignup">Signup</button></td>
              <td><button type="button" @click="userLogin">Login</button></td>
          </tr>
      </table>
  </div>
</template>

<script>
export default {
    name: 'Login',
    methods:{
        userLogin(){
            // login ethereum blockchain and BOOM data server
            // we use ethereum private key as ID to gain authorization for some operation
            // because private key are absolute secret, there is no need to set password
            
            // login API call

            // jump to default user interface:
            this.$emit('change-view','ListAndForm');
        },
        userSignup(){
            // change the view to signup page
            this.$emit('change-view','Signup');
        }
    }
}
</script>

<style>

</style>