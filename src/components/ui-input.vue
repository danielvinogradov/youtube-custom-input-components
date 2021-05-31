<template>

  <input
      class="ui-input"
      type="text"
      :value="username"
      @input="$emit('update:username', $event.target.value)"
  >

</template>

<script>
  export default {
    name: "ui-input",
    props: {
      username: { type: String, default: null, },
    }
  }
</script>

<style lang="scss" scoped>
  .ui-input {
    padding: 10px;
    font-size: 18px;
    border-radius: 5px;
    border: 1px solid #2c3e50;
    outline: none;

    &:focus {
      box-shadow: 0 0 15px #2c3e50;
    }
  }
</style>