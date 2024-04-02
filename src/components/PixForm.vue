<template>
  <div>
    <form @submit.prevent="generateQRCode">
      <v-row>
        <v-col cols="3">
          <label class="label" for="chave">QR code</label>
        </v-col>
      </v-row>
    </form>
  </div>
</template>
<style scoped>

.label {
  font-weight: bolder;
  padding-right: 10px;
  padding-bottom: 10px;
}
</style>
