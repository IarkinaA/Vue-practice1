<template>
  <div>
    <button @click="upCounter">Значение счетчика: {{ counter }}</button>
  </div>
</template>

<script>
export default {
  name: 'InterComp',

  data() {
    return {
      counter: 0,
    };
  },

  

  methods: {
    upCounter() {
      this.counter++
    }
  },
  beforeCreate() {
    this.counter = 1;
  }
};
</script>

<style lang="css" scoped>

</style>