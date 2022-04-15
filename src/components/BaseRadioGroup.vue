<template>
  <component
    :class="{horizontal:!vertical}"
    v-for="option in options"
    :key="option.value"
    :is="vertical ? 'div':'span'"
  >
    <BaseRadio
      :value="option.value"
      :label="option.label"
      :name="name"
      :modelValue="modelValue"
      @update:modelValue="$emit('update:modelValue',$event)"
    />
  </component>
</template>

<script>
export default {
  name: 'BaseRadioGroup',
  props: {
    options: {
      type: Array,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    modelValue: {
      type: [Number, String],
      default: ''
    },
    vertical: {
      type: Boolean,
      default: false
    }

  }

}
</script>

<style scoped>
.horizontal {
margin-right: 10px;
}
</style>
