<template>
  <ul class="list-disc list-inside">
    <li v-for="item in items" :key="item.to">
      <external-link :href="item.to" :text="item.text" />

      <template v-if="item.description">
        <span class="mx-1 select-none">-</span>
        <span v-text="item.description" />
      </template>
    </li>
  </ul>
</template>

<script lang="ts">
import Vue from 'vue'
import ExternalLink from '~/components/external-link.vue'

export default Vue.extend({
  name: 'LinksList',

  components: {
    ExternalLink,
  },

  props: {
    items: {
      required: true,
      type: Array,
    },
  },
})
</script>
