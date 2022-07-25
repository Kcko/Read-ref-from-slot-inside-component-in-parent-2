<!-- HelloWorld.vue -->
<template>
  <slot></slot>
  <hr />
  <h2>Hello world</h2>
  <input type="text" ref="test2" @change="handleChange" />

  <button @click="handleChange">ZZZ</button>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: ['test', 'test2'],
  mounted() {
    console.log('REF FROM PARENT AKA SLOT ', this.$props);
    this.$refs.test2.value = 'test 2 value';
  },
  methods: {
    handleChange() {
      console.log(this.$props);
    },
  },
  watch: {
    test: (comp) => {
      if (comp) {
        comp.value = 'test 1 value';
      }
    },
  },
};
</script>
