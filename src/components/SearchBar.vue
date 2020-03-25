<template>
  <div>
      <input class="form-control my-3" @input="onInput"/>
  </div>
</template>
<script>
export default {
    name: "SearchBar",
    methods: {
        onInput: function(event) {
            this.$emit('termChange', event.target.value)
        }
    }
}
</script>
<style scoped>

</style>