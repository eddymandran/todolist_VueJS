<template>
  <div v-show="visible">
      index: {{ index}}
    <slot></slot>
  </div>
</template>

<script>
export default {
  data () {
    return {
      index: 0
    }
  },
  computed: {
    visible () {
      return this.index === this.$parent.index
    }
  }
}
</script>
