<template>
  <div class="payment">
    <h1>Checkout</h1>
    <div style="justify-content: center; display: grid;">
    <div v-if="step === 1">
      <h2>Escolha a opção de pagamento:</h2>
      <div class="payment-option-container">
        <div v-for="option in paymentOptions" :key="option.method" class="payment-option">
          <img :src="option.icon" :alt="option.alt">
          <button class="payment-buttons" @click="choosePayment(option.method)">{{ option.label }}</button>
        </div>
      </div>
    </div>
    <div v-else-if="step === 2">
      <h2 class="title-information">Preencher informações adicionais:</h2>
      <component :is="paymentMethodFormComponent"></component>
      <button class="confirm-credit-payment" @click="confirmPayment">Confirmar Pagamento</button>
    </div>
    </div>
    <!-- Adicione outras etapas aqui -->
  </div>
</template>

<script>
import CreditCardForm from './CreditCardForm.vue'; // Importar componente para formulário de cartão de crédito
import BoletoForm from './BoletoForm.vue'; // Importar componente para formulário de boleto
import PixForm from './PixForm.vue'; // Importar componente para formulário de Pix

export default {
  data() {
    return {
      step: 1,
      paymentMethod: null,
      creditCard: {
        number: '',
        cvv: '',
        expiryDate: '',
        cardHolderName: '',
        cpf: '',
        installments: 1,
      },
      boleto: {
        cpf: '',
        name: '',
        lastName: '',
        email: '',
        barcode: '',
        dueDate: '',
      },
      pix: {
        qrCode: '',
        expirationTime: '',
      },
      products: [],
      purchaseDate: '',
      deliveryDate: '',
      paymentOptions: [
        {
          method: 'cartao',
          label: 'Cartão de Crédito',
          icon: require('@/assets/credit-card.png'),
          alt: 'Ícone de cartão de crédito',
          formComponent: 'CreditCardForm',
          styleClass: 'pix-icon', // Adicionando uma classe CSS para o ícone do Pix

        },
        {
          method: 'boleto',
          label: 'Boleto',
          icon: require('@/assets/boleto.jpg'),
          alt: 'Ícone de boleto',
          formComponent: 'BoletoForm',
          styleClass: 'pix-icon', // Adicionando uma classe CSS para o ícone do Pix

        },
        {
          method: 'pix',
          label: 'Pix',
          icon: require('@/assets/pix-icon.png'),
          alt: 'Ícone de Pix',
          formComponent: 'PixForm',
          styleClass: 'pix-icon', // Adicionando uma classe CSS para o ícone do Pix

        },
      ],
    };
  },
  computed: {
    paymentMethodFormComponent() {
      if (this.paymentMethod) {
        return this.paymentOptions.find(option => option.method === this.paymentMethod).formComponent;
      }
      return null;
    }
  },
  methods: {
    choosePayment(method) {
      this.paymentMethod = method;
      this.step = 2;
    },
    confirmPayment() {
      // Lógica para confirmar o pagamento
      this.step = 3;
    },
  },
  components: {
    CreditCardForm,
    BoletoForm,
    PixForm,
  },
};
</script>

<style scoped>

#app > div > div > div > div > div > div:nth-child(1) > img,
#app > div > div > div > div > div > div:nth-child(2) > img,
#app > div > div > div > div > div > div:nth-child(3) > img
{
  height: 30px!important;
  width: 30px!important;
}
.payment-option{
  display: flex;
  padding-bottom: 10px;
}
.payment-buttons{
  margin-left: 10px;
  cursor: pointer;
  
}
.confirm-credit-payment{ 
  height: 40px;
  cursor: pointer;
  border: 1px solid rgb(0, 0, 0);
  padding: 10px;
  border-radius: 5px;
}
.title-information{
  padding-bottom: 20px;
}
</style>
