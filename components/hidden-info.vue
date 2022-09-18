<template>
  <button
    v-if="!visible"
    class="px-3 rounded bg-gray-200 hover:bg-gray-500 hover:text-gray-100"
    type="button"
    @click="visible = true"
    v-text="text"
  />

  <input
    v-else
    class="px-2 py-px w-full border border-gray-300 rounded-lg focus:ring"
    readonly
    size="33"
    :value="value"
    @focus="onFocus"
  />
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    value: {
      required: true,
      type: String,
    },
  },

  data: () => ({
    text: 'Show',
    visible: false,
  }),

  methods: {
    onFocus({ target }: FocusEvent) {
      requestAnimationFrame(() => {
        ;(target as HTMLInputElement).setSelectionRange(0, this.value.length)
      })
    },
  },
})
</script>
