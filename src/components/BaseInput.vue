<template>
  <div>
    <label>{{ label }}</label>
    <input
      v-bind="$attrs"
      :value="modelValue"
      :placeholder="label"
      @input="$emit('update:modelValue',$event.target.value)"
    >
  </div>
</template>

<script>
export default {
  inheritAttrs: false,
  name: 'BaseInput',
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number]
    }
  }
}
</script>

<style scoped>

</style>
