<template>
  <div class="home">
    <PaymentCheckout />
  </div>
</template>

<script>
// @ is an alias to /src
import PaymentCheckout from '@/components/PaymentCheckout.vue'

export default {
  name: 'HomeView',
  components: {
    PaymentCheckout
  }
}
</script>
