<template>
  <div id="app" style="font-size:20px;">
    <!-- v-for directive -->
    <p v-for="(item, index) in list" :key="index">{{item}}</p>
    <!-- v-if directive -->
    <button v-on:click="toggle">Clickame</button>
    <h1 v-if="isOn">HELLO</h1>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      list: ["Batatas", "Cenouras", "Couves"],
      isOn: false
    };
  },
  methods: {
    toggle() {
      this.isOn = !this.isOn;
    }
  }
};
</script>

<style>
</style>
