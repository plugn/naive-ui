<markdown>
# Focus & blur & select manually
</markdown>

<template>
  <n-space vertical>
    <n-space>
      <n-button @click="handleFocus">
        Focus
      </n-button>
      <n-button :focusable="false" @click="handleBlur">
        Blur
      </n-button>
      <n-button :focusable="false" @click="handleSelect">
        Select
      </n-button>
    </n-space>
    <n-input ref="inputInstRef" v-model:value="inputValue" />
  </n-space>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import { InputInst } from 'naive-ui'

export default defineComponent({
  setup () {
    const inputInstRef = ref<InputInst | null>(null)
    return {
      inputInstRef,
      inputValue: ref("I heard you're going to select all?"),
      handleFocus () {
        inputInstRef.value?.focus()
      },
      handleBlur () {
        inputInstRef.value?.blur()
      },
      handleSelect () {
        inputInstRef.value?.select()
      }
    }
  }
})
</script>
