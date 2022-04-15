<template>
<div>
  <input type="checkbox" :checked="modelValue" @change="$emit('update:modelValue',$event.target.checked)">
  <label v-if="label">{{label}}</label>
  </div>
</template>

<script>
export default {
  name: 'BaseCheckbox',
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>

</style>
