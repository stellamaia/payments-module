<template>
  <div>
    <form @submit.prevent="generateQRCode">
      <v-row>
        <v-col cols="3">
      <label class="label" for="chave">Chave Pix:</label>
    </v-col>
        <v-col cols="9">
      <input class="input" type="text" id="chave" v-model="formData.chave">
    </v-col>
  </v-row>


 <v-row>
        <v-col cols="3">
      <label  class="label"  for="valor">Valor:</label>
    </v-col>
        <v-col cols="9">
      <input class="input"  id="valor" v-model="formData.valor">
    </v-col>
  </v-row>


  <v-row>
  <v-col cols="3">
      <button type="submit">Gerar QRCode</button>
    </v-col>
  </v-row>
    </form>

  </div>
</template>

<script>

export default {
  data() {
    return {
     
    };
  },

};
</script>
<style scoped>

.input {
  background: rgb(238, 236, 236);
  outline: none;
  height: 25px;
}
.label {
  font-weight: bolder;
  padding-right: 10px;
  padding-bottom: 10px;
}

</style>