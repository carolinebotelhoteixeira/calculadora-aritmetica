<template>
  <div id="app" class="container mt-5 p-4 border rounded shadow bg-light">
    <h1 class="text-center mb-4">Calculadora Aritmética</h1>
    <div class="form">
      <div class="mb-3">
        <input
          type="number"
          class="form-control"
          v-model.number="numero1"
          placeholder="Digite o primeiro número"
        />
      </div>
      <div class="mb-3">
        <select class="form-select" v-model="operacao">
          <option value="+">Soma</option>
          <option value="-">Subtração</option>
          <option value="*">Multiplicação</option>
          <option value="/">Divisão</option>
        </select>
      </div>
      <div class="mb-3">
        <input
          type="number"
          class="form-control"
          v-model.number="numero2"
          placeholder="Digite o segundo número"
        />
      </div>
    </div>
    <ResultadoCalculadora :resultado="calcular" />
  </div>
</template>

<script>
import ResultadoCalculadora from "./components/Resultado.vue"; // Nome atualizado

export default {
  components: {
    ResultadoCalculadora, // Nome atualizado
  },
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: "+",
    };
  },
  computed: {
    calcular() {
      switch (this.operacao) {
        case "+":
          return this.numero1 + this.numero2;
        case "-":
          return this.numero1 - this.numero2;
        case "*":
          return this.numero1 * this.numero2;
        case "/":
          return this.numero2 !== 0
            ? (this.numero1 / this.numero2).toFixed(2)
            : "Divisão por zero";
        default:
          return 0;
      }
    },
  },
};
</script>

<style scoped>
.container {
  max-width: 400px;
  margin: auto;
  background-color: #f9f9f9;
  border: 2px solid #ddd;
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

h1 {
  color: #333;
  margin-bottom: 20px;
}

.form {
  display: flex;
  flex-direction: column;
}

input,
select {
  padding: 10px;
  font-size: 16px;
}

input:focus,
select:focus {
  border-color: #007bff;
  outline: none;
  box-shadow: 0 0 5px rgba(0, 123, 255, 0.5);
}
</style>

