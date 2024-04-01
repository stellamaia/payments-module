<template>
  <div style="text-align: start;">
    <div class="boleto-information-container">
      <v-row>
        <v-col cols="3">
          <label class="label">CPF:</label>
        </v-col>
        <v-col cols="7">
          <input class="input" type="text" v-model="formData.cpf">
        </v-col>
      </v-row>
    </div>

    <div class="boleto-information-container">
      <v-row>
        <v-col cols="3">
      <label class="label">Nome:</label>
    </v-col>
        <v-col cols="7">
      <input class="input" type="text" v-model="formData.name">
    </v-col>
      </v-row>
    </div>

    <div class="boleto-information-container">
      <v-row>
        <v-col cols="3">
      <label class="label">Sobrenome:</label>
    </v-col>
        <v-col cols="7">
      <input  class="input" type="text" v-model="formData.lastName">
    </v-col>
      </v-row>
    </div>

    <div class="boleto-information-container">
      <v-row>
        <v-col cols="3">
      <label class="label">E-mail:</label>
    </v-col>
        <v-col cols="7">
      <input class="input" type="text" v-model="formData.email">
    </v-col>
      </v-row>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        cpf: '',
        name: '',
        lastName: '',
        email: '',
      }
    };
  }
};
</script>
<style scoped>
.boleto-information-container {
  padding-bottom: 10px;
}
.label{
  font-weight: bolder;
  padding-right: 10px;
  padding-bottom: 10px;
}


.input {
  background: rgb(238, 236, 236);
  outline: none;
  height: 25px;
}
</style>