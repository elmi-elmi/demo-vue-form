<template>
  <div>
    <label v-if="label">{{ label }}</label>
    <select class="field" :value="modelValue"
            v-bind="{...$attrs,onchange:$event=>$emit('update:modelValue', $event.target.value)}">
      <option v-for="option in options" :key="option" :value="option">{{ option }}</option>
    </select>
  </div>
</template>

<script>
export default {
  inheritAttrs: false,
  name: 'BaseSelect',
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number]
    },
    options: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>

</style>
