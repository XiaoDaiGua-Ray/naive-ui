<markdown>
# Use preset card

Modal has some presets, which means you can use props & slots of the preset after set it.
</markdown>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  setup() {
    return {
      bodyStyle: {
        width: '600px'
      },
      segmented: {
        content: 'soft',
        footer: 'soft'
      } as const,
      showModal: ref(false)
    }
  }
})
</script>

<template>
  <n-button @click="showModal = true">
    Start me up
  </n-button>
  <n-modal
    v-model:show="showModal"
    class="custom-card"
    preset="card"
    :style="bodyStyle"
    title="Modal"
    :bordered="false"
    size="huge"
    :segmented="segmented"
  >
    <template #header-extra>
      Oops!
    </template>
    Content
    <template #footer>
      Footer
    </template>
  </n-modal>
</template>
