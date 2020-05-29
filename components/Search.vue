<template>
  <div class="w-full relative">
    <label for="search" class="sr-only">Buscar</label>
    <div class="relative">
      <div
        class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none"
      >
        <svg
          fill="none"
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          viewBox="0 0 24 24"
          class="h-5 w-5 text-gray-500"
        >
          <path d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
        </svg>
      </div>
      <input
        id="search"
        placeholder="Procure uma categoria aqui!"
        type="search"
        v-model="q"
        @input="doSearch()"
        autocomplete="off"
        class="block w-full pl-10 pr-3 py-2 truncate leading-5 placeholder-gray-500 border border-transparent text-gray-700 dark:text-white dark-focus:text-white focus:border-gray-300 dark-focus:border-gray-700 rounded-md focus:outline-none focus:bg-white dark-focus:bg-gray-900 bg-gray-200 dark:bg-gray-800"
      />
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      q: ''
    }
  },
  methods: {
    doSearch() {
      this.$emit('doSearch', this.q)
    }
  }
}
</script>
