<template>
  <div id='app'>
  <input v-model="form.body" />

  <button @click="addItem">Add Item</button>

  <li v-for="Item in Items" :key="Item.$id">
  {{item.body}}
  </li>
  </div>
</template>

<script>
import Item from './classes/item'

export default {
  name: 'App',

  data() {
  
    return {

      form: {

       body: ''
      }
    }
  },

  computed: {
     items() {
     return Item.all()
     }

  },

  methods: {

    additem() {
    Item.insert({data: this.form})
    
    }
  }
}
</script>


