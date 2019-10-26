<template>
  <div id="app" style="font-size:20px;">
    <!-- v-for directive -->
    <div v-if="isOn">
    <p v-for="(item, index) in list" :key="index">{{item}}</p>
    </div>
    <!-- v-if directive -->
    <button v-on:click="toggle">Clickame</button>
    <h1 v-if="isOn">HELLO</h1>
 
  <p>Enter your markdown code</p>

  <textarea name="editor" id="editor" cols="60" rows="10" v-on:keyup="transformMarkdown" v-model="input"></textarea>
  <div id="preview" ref="preview"></div>
 </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      list: ["Batatas", "Cenouras", "Couves"],
      isOn: false,
      input: ""
    };
  },
  methods: {
    toggle() {
      this.isOn = !this.isOn;
    },
    transformMarkdown(event){
      console.log(event);
      console.log(this.$refs.preview)
      this.$refs.preview.innerHTML = marked(this.input, {breaks: true}); 
    }
  }
}
</script>

<style>
</style>
