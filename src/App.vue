<template>
  <div class="container">
    <h1>Generator kodu QR</h1>
    <img ref="img" src="" alt="" />
    <input ref="input" type="text" placeholder="Wprowadź URL" />
    <button @click="createQr" class="btn">Wygeneruj</button>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},

  mounted() {},
  data() {
    return {};
  },
  methods: {
    createQr() {
      const api = "http://api.qrserver.com/v1/";
      const restOfApi = "create-qr-code/?data=";
      const img = this.$refs.img;
      const input = this.$refs.input.value;
      img.src = `${api}${restOfApi}${input}`;
      console.log(img, input);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
