<template>
  <div class="pt-16">
    <Header>
      <template v-slot:search>
        <Search @doSearch="doSearch"></Search>
      </template>
    </Header>
    <main class="container mx-auto px-4 lg:px-8">
      <div class="container">
        <div
          class="grid w-full lg:w-3/4 py-4 lg:pt-8 lg:pb-4"
          v-if="filteredStores.length > 0"
        >
          <div
            class="grid__item relative shadow-lg"
            v-for="(store, i) in filteredStores"
            :key="i"
          >
            <StoreItem :store="store"></StoreItem>
            <SocialBadges
              v-if="!!store.social === true"
              :social="store.social"
            ></SocialBadges>
          </div>
        </div>
        <div class="w-full py-4 lg:pt-8 lg:pb-4" v-else>
          <EmptyList></EmptyList>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import Search from '~/components/Search.vue'
import Header from '~/components/Header.vue'
import EmptyList from '~/components/EmptyList.vue'
import SocialBadges from '~/components/SocialBadges.vue'
import StoreItem from '~/components/StoreItem.vue'
export default {
  components: {
    Header,
    EmptyList,
    Search,
    SocialBadges,
    StoreItem
  },
  data() {
    return {
      stores: [],
      q: ''
    }
  },
  async fetch() {
    const { list } = await this.$content('stores').fetch()
    this.stores = list
  },
  methods: {
    doSearch(query) {
      this.q = query
    }
  },
  computed: {
    filteredStores: function() {
      if (this.q !== '') {
        return this.stores.filter(s =>
          s.category.toLowerCase().includes(this.q)
        )
      } else {
        return this.stores
      }
    }
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.header {
  height: 64px;
}
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
.social {
  margin-top: 8px;
  max-width: 100px;
  bottom: 16px;
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
@media (max-width: 767px) {
  .grid {
    grid-template-columns: 1fr;
    padding: 0 16px;
  }
}
</style>
