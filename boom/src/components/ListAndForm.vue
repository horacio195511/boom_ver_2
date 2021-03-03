<template>
<div>
    <!--Sidebar, should be expandable-->
    <div>
        <button type="button">Thing</button>
        <button type="button">Order</button>
        <button type="button">Printer</button>
        <!--Manager Only-->
        <button type="button">News</button>
    </div>
    <!--List-->
    <!--Form, could be news, order, printer, thing-->
    <component
        :is="formtype" 
        :item="selectedItem"
    ></component>
</div>
</template>

<script>
import ListItem from './Item/ListItem.vue'
import NewsForm from './Form/NewsForm'
import OrderForm from './Form/OrderForm'
import PrinterForm from './Form/PrinterForm'
import ThingForm from './Form/ThingForm'

export default {
    name: 'ListAndForm',
    module: {
        ListItem, NewsForm, OrderForm, PrinterForm, ThingForm
    },
    props:['formtype'],

}
</script>

<style>

</style>