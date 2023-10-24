<template>
  <form @submit.prevent="downloadBarCode" class="form">
    <h1>Type to view BarCode</h1>
    <div ref="barCodeDiv">
      <vue-barcode
        ref="BarImg"
        v-if="barcodeValue"
        tag="img"
        :value="barcodeValue"
        :options="{ displayValue: true, lineColor: '#2B2B2C' }"
      />
    </div>
    <input type="text" v-model="barcodeValue" />
    <button v-if="barcodeValue" @click="saveBarCode">Save BarCode</button>
  </form>
</template>

<script>
import { ref } from "vue";
import VueBarcode from "@chenfengyuan/vue-barcode";

export default {
  name: 'BarcodeGenerator',
  setup() {
    const barcodeValue = ref(null);

    const downloadBarCode = () => {
      // Implement your downloadBarCode function logic here
    };

    const saveBarCode = () => {
      // Implement your saveBarCode function logic here
    };

    return {
      barcodeValue,
      downloadBarCode,
      saveBarCode,
    };
  },
  components: {
    "vue-barcode": VueBarcode,
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.form {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
button {
  height: 40px;
  width: 310px;
  background-color: green;
  color: white;
  border: none;
  border-radius: 0.5rem;
  font-size: medium;
  display: block;
  margin-top: 1.3rem;
}
input {
  height: 30px;
  width: 300px;
  padding: 5px;
  font-size: 1rem;
  border-radius: 7px;
}
</style>
