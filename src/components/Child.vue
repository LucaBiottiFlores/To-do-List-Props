<template>
  <div id="Child">
    <div class="d-flex flex-column justify-content-center flex-wrap">
      <h2 class="listTitle my-5">Lista</h2>
      <div
        class="
          listContainer
          d-flex
          flex-column
          justify-content-center
          flex-wrap
          px-5
          mx-5
        "
      >
        <ul class="list d-flex justify-content-center flex-column">
          <li
            class="listItem my-1 d-flex justify-content-start"
            v-for="(item, $index) in items"
            :key="$index"
          >
            {{ $index }}) {{ item }}
            <button
              @click="$emit('eliminar')"
              class="liBtn ms-auto me-3"
              type="button"
            >
              Eliminar
            </button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Child',
  data: () => ({}),

  props: {
    items: {
      type: Array,
      required: true
    }
  }
}
</script>

<style>
.listTitle {
  text-align: center;
}
.liBtn {
  background: rgba(184, 233, 134, 0.25);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  border-radius: 10px;
}

</style>
