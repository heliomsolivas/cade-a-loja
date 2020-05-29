<template>
  <div class="social flex flex-1">
    <a
      v-if="social.instagram"
      target="_blank"
      :href="`https://instagram.com/${social.instagram}`"
    >
      <img width="24" class="mr-2" src="@/assets/icons/instagram.png" />
    </a>
    <a
      v-if="social.phone"
      target="_blank"
      class="mr-2"
      :href="`https://api.whatsapp.com/send?phone=${social.phone}`"
      ><img width="24" src="@/assets/icons/whatsapp.png"
    /></a>
    <a
      target="_blank"
      :href="`https://facebook.com/${social.facebook}`"
      v-if="social.facebook"
    >
      <img class="mr-2" width="24" src="@/assets/icons/facebook.png" />
    </a>
    <img
      v-if="social.ifood"
      width="24"
      class="mr-2"
      src="@/assets/icons/ifood.png"
    />
    <img
      v-if="social.aiqfome"
      width="24"
      class="mr-2"
      src="@/assets/icons/aiqfome.png"
    />
  </div>
</template>

<script>
export default {
  props: {
    social: {
      type: Object,
      default: {}
    }
  },
  data() {
    return {}
  },
  computed: {},
  methods: {}
}
</script>
