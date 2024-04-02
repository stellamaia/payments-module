<template>

  <div>

    <v-container>
      <v-form ref="form">
        <v-row>
          <v-col cols="12" sm="12">
            <v-text-field v-model="formData.cpf" label="CPF"></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" sm="12">
            <v-text-field v-model="formData.name" label="Nome"></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" sm="12">
            <v-text-field v-model="formData.lastName" label="Sobrenome"></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" sm="12">
            <v-text-field v-model="formData.email" label="E-mail"></v-text-field>
          </v-col>
        </v-row>
      </v-form>

    </v-container>
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

.label {
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