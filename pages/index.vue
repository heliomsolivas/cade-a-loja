<template>
  <div class="container">
    <div class="grid">
      <div class="grid__item" v-for="(store, i) in stores" :key="i">
        {{ store.name }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      stores: []
    }
  },
  async fetch() {
    const { list } = await this.$content('stores').fetch()
    this.stores = list
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.grid {
  width: 100%;
  position: relative;
  max-width: 1760px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  grid-gap: 16px;
  margin: 0px auto;
}
.grid__item {
  background-color: #ffffff;
  border: 1px solid #f7f7f7;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.08);
  color: #222222;
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
