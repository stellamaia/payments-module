<template>
  <div class="credit-card-container">
    <v-form ref="form" v-model="valid" lazy-validation>
      <v-select v-model="flags" :items="listFlags" label="Bandeira" :rules="flagsRules"></v-select>

      <v-text-field v-model="number" :rules="numberRules" label="Número do Cartão" required></v-text-field>

      <v-row>
        <v-col cols="6">
          <v-text-field v-model="cvv" :counter="3" label="CVV" :rules="cvvRules" required></v-text-field>
        </v-col>
        <v-col cols="6">
          <v-text-field v-model="expiryDate" label="Vencimento" :rules="expiryDateRules" required
            hint="Formato: MM/YYYY"></v-text-field>
        </v-col>
      </v-row>

      <v-text-field v-model="name" label="Nome" :rules="nameRules" required></v-text-field>


      <v-row>
        <v-col cols="6">
          <v-text-field v-model="cpf" :counter="11" label="CPF" :rules="cpfRules" required></v-text-field>
        </v-col>
        <v-col cols="6">
          <v-text-field v-model="cnpj" :counter="14" label="CNPJ" :rules="cnpjRules" required></v-text-field>
        </v-col>
      </v-row>
      <v-btn class="confirm-credit-payment" @click="confirmPayment"  >Confirmar Pagamento</v-btn>

    </v-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      listFlags: ['Mastercard', 'Visa'],
      flags: '',
      number: '',
      cvv: '',
      expiryDate: '',
      name: '',
      cpf: '',
      cnpj: '',
      valid: false, // Define se o formulário é válido ou não
      showErrorMessage: false, // Variável para controlar a exibição da mensagem de erro

      flagsRules: [
        v => !!v || 'Bandeira é obrigatória',

      ],
      numberRules: [
        value => !!value || 'Número do cartão é obrigatório',
        value => {
          const cleanedNumber = value.replace(/\s|-/g, '');
          if (!cleanedNumber.match(/^\d{13,16}$/)) {
            return ' número de cartão inválido. Deve ter entre 13 e 16 dígitos.';
          }
          return true;
        }
      ],
      cvvRules: [
        v => !!v || 'CVV é obrigatório',
        v => v.length === 3 || 'CVV deve ter 3 dígitos'
      ],
      expiryDateRules: [
        v => !!v || 'Data de validade é obrigatória',
        v => /^(0[1-9]|1[0-2])\/20[2-9][0-9]$/.test(v) || 'Formato de data inválido (MM/YYYY)'

      ],
      nameRules: [
        v => !!v || 'Nome é obrigatório', // Verifica se o campo não está vazio
      ],
      cpfRules: [
        v => !!v || 'CPF é obrigatório', // Verifica se o campo não está vazio
        v => v.length === 11 || 'CPF deve conter 11 digitos'

      ],
      cnpjRules: [
        v => !!v || 'CNPJ é obrigatório', // Verifica se o campo não está vazio
        v => v.length === 14 || 'CNPJ deve ter 14 dígitos'

      ],

    };
  },
  methods: {
    confirmPayment() {
    // Verificar se o formulário é válido
    if (this.$refs[`form`].validate()) {
      
      // Se o formulário for válido, avance para o passo 3
      console.log('Formulário válido');
      this.step = 3;

    } 
    else{
      // Se o formulário não for válido, exiba mensagem
      console.log('Preencha todo o Formulário ');

    }
  }
  }

  
};
</script>

<style scoped>
.credit-card-container {
  padding-bottom: 40px;
}

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
