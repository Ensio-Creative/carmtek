<template>
  <div class="input-control">
    <label><slot /></label>
    <textarea
      v-if="controlType === 'input'"
      v-bind="$attrs"
      :value="value"
      rows="3"
      @input="$emit('input', $event.target.value)"
    />
  </div>
</template>

<script>
export default {
  name: 'AppTextAreaControl',
  props: {
    controlType: {
      type: String,
      default: 'input'
    },
    value: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped>
.input-control {
  margin: 10px 0;
}

.input-control label {
  display: block;
  font-weight: bold;
  font-size: 15px;
  padding: 10px 0px;
}

.input-control input,
.input-control textarea {
  display: block;
  background-color: #fff;
  width: 100%;
  box-sizing: border-box;
  font: inherit;
  padding: 5px;
  border-left: 0px;
  border-right: 0px;
  border-top: 0px;
  border-bottom: 1px solid var(--base-dark-gray) !important;
  border-radius: 0px;
}

.input-control input:focus,
.input-control textarea:focus {
  background-color: #E9E9E9;
  outline: none;
  border: 0px;
}
</style>
