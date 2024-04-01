<template>
  <div style="text-align: start;">
    <div class="information-container">
      <v-row>
        <v-col cols="6">
          <label class="label">Número do Cartão:</label>
        </v-col>
        <v-col cols="6">
          <input class="input" type="text" v-model="formData.number">
        </v-col>
      </v-row>
    </div>

    <div class="information-container">
      <v-row>
        <v-col cols="6">
          <label class="label">CVV:</label>
        </v-col>
        <v-col cols="6">
          <input class="input" type="text" v-model="formData.cvv">
        </v-col>
      </v-row>
    </div>

    <div class="information-container">
      <v-row>
        <v-col cols="6">
          <label class="label">Data de Vencimento:</label>
        </v-col>
        <v-col cols="6">
          <input class="input" type="text" v-model="formData.expiryDate">
        </v-col>
      </v-row>
    </div>

    <div class="information-container">
      <v-row>
        <v-col cols="6">
          <label class="label">Nome do Titular:</label>
        </v-col>
        <v-col cols="6">
          <input class="input" type="text" v-model="formData.cardHolderName">
        </v-col>
      </v-row>
    </div>


    <div class="information-container">
      <v-row>

        <v-col cols="6">
          <label class="label">CPF/CNPJ:</label>
        </v-col>

        <v-col cols="6">
          <input class="input" type="text" v-model="formData.cpf">
        </v-col>
      </v-row>
    </div>


    <div class="information-container">
      <v-row>

        <v-col cols="6">
          <label class="label">Número de Parcelas:</label>
        </v-col>

        <v-col cols="6">
          <input class="input" type="number" v-model="formData.installments">
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
        number: '',
        cvv: '',
        expiryDate: '',
        cardHolderName: '',
        cpf: '',
        installments: 1,
      }
    };
  }
};
</script>
<style scoped>
.label {
  font-weight: bolder;
  padding-right: 10px;
  padding-bottom: 10px;
}

.information-container {

  padding-bottom: 10px;
}

.input {
  background: rgb(238, 236, 236);
  outline: none;
  height: 25px;
}
</style>