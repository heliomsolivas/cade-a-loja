<template>
  <div class="grid__details mb-4">
    <div
      class="inline-block text-white p-2 mb-1 text-sm font-semibold rounded-sm"
      :class="getCategoryColor(store.category)"
    >
      {{ store.category }}
    </div>
    <div class="text-xl leading-tight mb-1">
      {{ store.name }}
      <img
        v-if="store.category === 'Japonesa'"
        class="inline-block"
        src="@/assets/icons/japan.png"
      />
      <img
        v-if="store.category === 'Pet'"
        class="inline-block"
        src="@/assets/icons/pet-shop.png"
      />
      <img
        v-if="store.category === 'Pizzaria'"
        class="inline-block"
        src="@/assets/icons/pizza.png"
      />
      <img
        v-if="store.category === 'Lanches'"
        class="inline-block"
        src="@/assets/icons/burger.png"
      />
    </div>
    <div class="text-sm leading-tight text-gray-600 mb-2">
      <span v-if="store.address">{{ store.address }} -</span>
      {{ store.city }}/{{ store.state }}
    </div>
    <div
      class="bg-gray-200 text-sm font-semibold text-gray-700"
      style="padding: 8px;border-radius:4px;display:inline-block;"
    >
      Entrega?
      <span v-if="store.delivery" style="color:green;">Sim! :)</span>
      <span v-else>Não :(</span>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  props: {
    store: {
      type: Object,
      default: {}
    }
  },
  data() {
    return {}
  },
  computed: {},
  methods: {
    getCategoryColor(category) {
      if (category === 'Açai') {
        return 'bg-purple-700'
      } else if (category === 'Pastelaria') {
        return 'bg-orange-700'
      } else if (category === 'Lanches') {
        return 'bg-red-700'
      } else {
        return 'bg-gray-700'
      }
    }
  }
}
</script>
