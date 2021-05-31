<template>
  <label>

    <input
        type="checkbox"
        :value="value"
        :checked="modelValue.includes(value)"
        @change="evt => onChange(evt.target.value)"
    >

    <slot/>
  </label>
</template>

<script>
  export default {
    name: "ui-checkbox",
    props: {
      value: { type: String, default: null, },
      modelValue: { type: Array, default: () => [], },
    },
    methods: {

      onChange(value) {
        if (this.modelValue.includes(this.value)) {
          this.$emit('update:modelValue', this.modelValue.filter(cv => cv !== value))
        }
        else {
          this.$emit('update:modelValue', this.modelValue.concat(value))
        }
      }

    }
  }
</script>

<style lang="scss" scoped>
  label {
    display: block;
    text-align: left;
  }
</style>