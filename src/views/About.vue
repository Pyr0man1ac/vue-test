<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h2>testDataOne: {{ testDataOne }}</h2>
    <button @click="change">change testDataOne</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      testDataOne: undefined
    };
  },
  watch: {
    // testDataOne(val) {
    //   console.log('first: ' + val)
    //   setTimeout(() => {
    //     console.log('delay: ' + val)
    //   }, 3000);
    // }
  },
  methods: {
    change() {
      this.testDataOne = Math.random();
    }
  },
  created() {
    alert("created");
  },
  activated() {
    alert("activated");
  },
  destroyed() {
    alert("destroyed");
  }
};
</script>
