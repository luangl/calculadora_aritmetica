<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-light text-center">
      <h2>Calculadora Aritmética</h2>
    </header>
    <div class="row bg-light">
      <div class="col-md-6">
        <label for="num1">Número 1:</label>
        <input type="number" class="form-control" id="num1" v-model="num1">
      </div>
      <div class="col-md-6">
        <label for="num2">Número 2:</label>
        <input type="number" class="form-control" id="num2" v-model="num2">
      </div>
    </div>
    <div class="row  bg-light mt-5">
      <div class="col-md-12">
        <label for="operacao">Operação:</label>
        <select class="form-control" id="operacao" v-model="operacao">
          <option value="soma">Soma</option>
          <option value="subtracao">Subtração</option>
          <option value="multiplicacao">Multiplicação</option>
          <option value="divisao">Divisão</option>
        </select>
      </div>
    </div>
    <div class="bg-light row mt-5">
      <div class="col-md-12">
        <h4>Resultado: {{ resultado }}</h4>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      num1: '',
      num2: '',
      operacao: 'soma'
    }
  },
  computed: {
    resultado() {
      let n1 = parseFloat(this.num1)
      let n2 = parseFloat(this.num2)
      let res = 0

      switch (this.operacao) {
        case 'soma':
          res = n1 + n2
          break
        case 'subtracao':
          res = n1 - n2
          break
        case 'multiplicacao':
          res = n1 * n2
          break
        case 'divisao':
          res = n1 / n2
          break
        default:
          res = 0
      }

      if (isNaN(res)) {
        return ''
      } else {
        return res.toFixed(2)
      }
    }
  },
  methods: {
    calcularResultado() {
    }
  }
}
</script>

