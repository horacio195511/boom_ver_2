<template>
  <div>
      <table>
          <tr>
              <td><label for="thing">Thing</label></td>
              <td>><input type="url" id="thing" v-model="thing"></td>
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
    name: 'CreateOrder',
    props: ['selectedItem'],
    methods: {
        addThing() {
            // connect to ethereum network
            // set network service provider: we use Metamask, which could be access through
            // window.ethereum
        },
        connectEther(){
            if(window.ethereum !== undefined){
                window.ethereum.enable();
            }
        },
        createThingOrder(){
            var Eth = require('web3-eth');
            console.log(Eth.givenProvider);
            var eth = new Eth(Eth.givenProvider);
            let time = Date.parse(this.time);
            // contract abi should be placed in external file
            var thingOrderContract = new eth.Contract(
                [
    {
      "inputs": [],
      "payable": false,
      "stateMutability": "nonpayable",
      "type": "constructor"
    },
    {
      "anonymous": false,
      "inputs": [],
      "name": "Abort",
      "type": "event"
    },
    {
      "anonymous": false,
      "inputs": [],
      "name": "ComingOrder",
      "type": "event"
    },
    {
      "anonymous": false,
      "inputs": [
        {
          "indexed": false,
          "internalType": "address payable",
          "name": "",
          "type": "address"
        }
      ],
      "name": "Dispatch",
      "type": "event"
    },
    {
      "anonymous": false,
      "inputs": [
        {
          "indexed": false,
          "internalType": "address payable",
          "name": "",
          "type": "address"
        }
      ],
      "name": "Making",
      "type": "event"
    },
    {
      "anonymous": false,
      "inputs": [
        {
          "indexed": false,
          "internalType": "address payable",
          "name": "",
          "type": "address"
        }
      ],
      "name": "Transporting",
      "type": "event"
    },
    {
      "constant": true,
      "inputs": [],
      "name": "currentState",
      "outputs": [
        {
          "internalType": "enum thingOrder.State",
          "name": "",
          "type": "uint8"
        }
      ],
      "payable": false,
      "stateMutability": "view",
      "type": "function"
    },
    {
      "constant": false,
      "inputs": [
        {
          "internalType": "uint256",
          "name": "_cartID",
          "type": "uint256"
        },
        {
          "internalType": "uint256",
          "name": "_amount",
          "type": "uint256"
        },
        {
          "internalType": "uint256",
          "name": "_thingID",
          "type": "uint256"
        },
        {
          "internalType": "string",
          "name": "_description",
          "type": "string"
        },
        {
          "internalType": "uint256",
          "name": "_deadline",
          "type": "uint256"
        }
      ],
      "name": "createOrder",
      "outputs": [
        {
          "internalType": "bool",
          "name": "",
          "type": "bool"
        }
      ],
      "payable": false,
      "stateMutability": "nonpayable",
      "type": "function"
    },
    {
      "constant": false,
      "inputs": [],
      "name": "cancelOrder",
      "outputs": [
        {
          "internalType": "uint256",
          "name": "",
          "type": "uint256"
        }
      ],
      "payable": false,
      "stateMutability": "nonpayable",
      "type": "function"
    },
    {
      "constant": false,
      "inputs": [],
      "name": "finishOrder",
      "outputs": [
        {
          "internalType": "uint256",
          "name": "",
          "type": "uint256"
        }
      ],
      "payable": false,
      "stateMutability": "nonpayable",
      "type": "function"
    }
  ], '0xD7DDAF0F3E3c643e2C41873D6173f0ec05364742'
            )
            thingOrderContract.methods.createOrder(
                this.cartID, this.amount, this.thingID, this.description, 100000)
                .send({from:Eth.givenProvider.selectedAddress})
                .then(console.log)
                .catch((error)=>{
                    console.error(error);   
                });
        }
    },
    computed: {
      opText(){
        if(selectedItem === undefined){
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