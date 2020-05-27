<template>
  <div class="container">
    <h1>Lista de Lojas</h1>
    <div class="grid">
      <div class="grid__item" v-for="(store, i) in stores" :key="i">
        <div class="badge">{{ store.category }}</div>
        <div class="name">{{ store.name }}</div>
        <div class="details">{{ store.address }}</div>

        <div class="social">
          <img width="32" src="@/assets/icons/instagram.png" />
          <a :href="`https://api.whatsapp.com/send?phone=${store.phone}`"
            ><img width="32" src="@/assets/icons/whatsapp.png"
          /></a>
          <img width="32" src="@/assets/icons/facebook.png" />
        </div>
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
h1 {
  margin-bottom: 32px;
  font-size: 32px;
}
.delivery {
  display: flex;
  font-family: Circular, -apple-system, BlinkMacSystemFont, Roboto,
    'Helvetica Neue', sans-serif !important;
  color: rgb(34, 34, 34) !important;
}
.social {
  margin-top: 8px;
  display: grid;
  grid-gap: 8px;
  grid-template-columns: 1fr 1fr 1fr;
  max-width: 120px;
}
.name {
  font-family: Circular, -apple-system, BlinkMacSystemFont, Roboto,
    'Helvetica Neue', sans-serif !important;
  font-weight: 400 !important;
  color: rgb(34, 34, 34) !important;
  font-size: 16px !important;
  line-height: 20px !important;
}
.badge {
  background-color: rgb(255, 255, 255) !important;
  color: rgb(34, 34, 34) !important;
  display: inline-block !important;
  font-family: Circular, -apple-system, BlinkMacSystemFont, Roboto,
    'Helvetica Neue', sans-serif !important;
  font-weight: 600 !important;
  text-transform: uppercase !important;
  text-align: center !important;
  padding-top: 1px !important;
  padding-bottom: 1px !important;
  padding-left: 5px !important;
  padding-right: 5px !important;
  font-size: 12px !important;
  line-height: 16px !important;
  border-radius: 4px !important;
  border-width: 1px !important;
  border-style: solid !important;
  border-color: rgb(34, 34, 34) !important;
  border-image: initial !important;
  margin-bottom: 8px;
}
.details {
  color: rgb(113, 113, 113) !important;
  line-height: 20px !important;
  max-height: 20px !important;
  text-overflow: ellipsis !important;
  display: -webkit-box !important;
  -webkit-line-clamp: 1 !important;
  -webkit-box-orient: vertical !important;
  animation-duration: 0.3s !important;
  animation-name: keyframe_18jn58a !important;
  animation-timing-function: ease-in-out !important;
  opacity: 1 !important;
  visibility: visible !important;
  flex: 1 1 0% !important;
  overflow: hidden !important;
}
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
  text-align: left;
  padding: 16px;
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  flex-direction: column;
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
