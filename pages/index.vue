<template>
  <div class="container">
    <!-- <input
      type="text"
      v-model="q"
      @input="$fetch"
      style="border:1px solid red;"
    /> -->
    <div class="grid w-full lg:w-3/4 py-4 lg:pt-8 lg:pb-4">
      <div
        class="grid__item relative shadow-lg"
        v-for="(store, i) in stores"
        :key="i"
      >
        <div class="grid__details mb-4">
          <div
            class="inline-block text-white p-2 mb-1 text-sm font-semibold rounded-sm"
            :class="getCategoryColor(store.category)"
          >
            {{ store.category }}
          </div>
          <div class="text-xl leading-tight mb-1">{{ store.name }}</div>
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

        <div class="social flex flex-1">
          <a
            v-if="store.instagram"
            target="_blank"
            :href="`https://instagram.com/${store.instagram}`"
          >
            <img width="24" class="mr-2" src="@/assets/icons/instagram.png" />
          </a>
          <a
            v-if="store.phone"
            target="_blank"
            class="mr-2"
            :href="`https://api.whatsapp.com/send?phone=${store.phone}`"
            ><img width="24" src="@/assets/icons/whatsapp.png"
          /></a>
          <img
            v-if="store.facebook"
            class="mr-2"
            width="24"
            src="@/assets/icons/facebook.png"
          />
          <img
            v-if="store.ifood"
            width="24"
            class="mr-2"
            src="@/assets/icons/ifood.png"
          />
          <img
            v-if="store.aiqfome"
            width="24"
            class="mr-2"
            src="@/assets/icons/aiqfome.png"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      stores: [],
      q: ''
    }
  },
  methods: {
    getCategoryColor(category) {
      if (category === 'Açai') {
        return 'bg-purple-700'
      } else if (category === 'Pastelaria') {
        return 'bg-orange-700'
      } else if (category === 'Restaurantes') {
        return 'bg-red-700'
      } else {
        return 'bg-gray-700'
      }
    }
  },
  async fetch() {
    const { list } = await this.$content('stores')
      .search(this.q)
      .fetch()
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
  color: #222222;
  display: inline-block;
  font-family: Circular, -apple-system, BlinkMacSystemFont, Roboto,
    Helvetica Neue, sans-serif;
  width: 100%;
  text-align: left;
  font-size: 40px;
  margin-top: 32px;
}
.delivery {
  display: flex;
  font-family: Circular, -apple-system, BlinkMacSystemFont, Roboto,
    'Helvetica Neue', sans-serif !important;
  color: rgb(34, 34, 34) !important;
}
.social {
  margin-top: 8px;
  max-width: 100px;
  bottom: 16px;
}
.name {
  font-family: Circular, -apple-system, BlinkMacSystemFont, Roboto,
    'Helvetica Neue', sans-serif !important;
  font-weight: 400 !important;
  color: rgb(34, 34, 34) !important;
  font-size: 16px !important;
  line-height: 20px !important;
  margin-bottom: 2px;
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
  color: rgb(113, 113, 113);
  line-height: 20px;
  max-height: 20px;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  animation-duration: 0.3s;
  animation-name: keyframe_18jn58a;
  animation-timing-function: ease-in-out;
  opacity: 1;
  visibility: visible;
  flex: 1 1 0%;
  overflow: hidden;
  margin-bottom: 4px;
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
  color: #222222;
  text-align: left;
  padding: 16px;
}
.grid__details {
  height: 156px;
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
@media (max-width: 767px) {
  .grid {
    grid-template-columns: 1fr;
    padding: 0 16px;
  }
}
</style>
