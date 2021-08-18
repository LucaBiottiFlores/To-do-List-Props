<template>
  <div id="Parent">
    <div class="container justify-content-center d-flex">
      <div class="mt-5 pt-5">
        <div class="d-flex justify-content-center">
          <input
            class="formInput px-3 mx-3"
            placeholder="Ingrese una nueva tarea"
            v-model="newItem"
          />
          <button @click="addItem" type="button" class="formBtn">Crear</button>
        </div>
        <Child :items="items" @eliminar="deleteItem"></Child>
      </div>
    </div>
  </div>
</template>

<script>
import Child from './Child.vue'

export default {
  name: 'Parent',
  data: () => ({
    items: [],
    newItem: ''
  }),

  components: {
    Child
  },

  methods: {
    addItem() {
      this.items.push(this.newItem)
      this.newItem = ''
    },

    deleteItem() {
      this.items.splice(this.items.indexOf(this.newItem), 1)
    }
  }
}
</script>

<style>
.formInput {
  width: 350px;
  background: rgba(255, 255, 255, 0.25);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border-radius: 10px;
}

.formBtn {
  width: 200px;
  background: rgba(184, 233, 134, 0.25);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border-radius: 10px;
}

.container {
  background: rgba(255, 255, 255, 0.25);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border-radius: 10px;
}
</style>
