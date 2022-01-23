<template>
<div>
    <!--Sidebar, should be expandable-->
    <div class="center">
        <button type="button" @click="toThing">Thing</button>
        <button type="button" @click="toOrder">Order</button>
        <button type="button" @click="toPrinter">Printer</button>
        <button type="button" @click="toMarket">Market</button>
        <!--Manager Only-->
        <button type="button" @click="toNews">News</button>
    </div>
    <div class="row">
        <div class="column left">
            <component
                :is="listtype"
            ></component>
        </div>
        <div class="column right">
            <component
                :is ="formtype"
                :selectedItem ="selectedItem"    
            ></component>
        </div>
    </div>
</div>
</template>

<script>
import Item from './Item/Item.vue'
import NewsForm from './Form/NewsForm.vue'
import OrderForm from './Form/OrderForm.vue'
import PrinterForm from './Form/PrinterForm.vue'
import ThingForm from './Form/ThingForm.vue'
import NewsList from './List/NewsList.vue'
import OrderList from './List/OrderList.vue'
import PrinterList from './List/PrinterList.vue'
import ThingList from './List/ThingList.vue'

export default {
    name: 'ListAndForm',
    components: {
        Item,
        NewsForm,
        OrderForm,
        PrinterForm,
        ThingForm,
        NewsList,
        OrderList,
        PrinterList,
        ThingList
    },
    data(){
        return {
            formtype: 'ThingForm',
            listtype: 'ThingList',
            selectedItem: undefined,
        }
    },
    methods: {
        toThing(){
            this.formtype = 'ThingForm';
            this.listtype = 'ThingList';
        },
        toOrder(){
            this.formtype = 'OrderForm';
            this.listtype = 'OrderList';
        },
        toPrinter(){
            this.formtype = 'PrinterForm';
            this.listtype = 'PrinterList';
        },
        toMarket(){
            this.formtype = 'OrderForm';
            this.listtype = 'ThingList';
        },
        toNews(){
            // validate the user, only content manager could edit News
            this.formtype = 'NewsForm';
            this.listtype = 'NewsList';
        }
    }
}
</script>

<style>
.row{
  display: flex;
  height: 100%;
}
.column{
  flex: 100%;
}
.left{
  flex: 70%;
  margin: auto;
}
.right{
  flex: 30%;
  margin:auto;
  border-left: 1px solid black;
}
</style>