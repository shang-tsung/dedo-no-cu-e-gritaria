<template>
  <div class="container-sm p-5 row">
    <form class="col-sm-12 col-lg-6">
      <h1 class="mb-4">Sobre o atendimento</h1>
      <h5 class="bold mb-4">Detalhes do atendimento</h5>

      <div class="mb-4">
        <div class="col">
          <label for="especialidade" class="form-label"
            >Especialidade principal*</label
          >
          <select
            v-model="especialidadeSelecionado"
            class="form-select"
            id="especialidade"
            required
          >
            <option value="" disabled selected>
              Selecione a especialidade
            </option>
            <option
              :value="especialidade"
              v-for="(especialidade, index) in especialidades"
              :key="index"
            >
              {{ especialidade }}
            </option>
          </select>
        </div>
      </div>
      <label for="especialidade" class="form-label my-3"
        >Informe o valor da consulta*</label
      >
      <div class="input-group mb-3 w-75">
        <span class="input-group-text">R$</span>
        <input
          type="text"
          class="form-control"
          placeholder="Valor"
          aria-label="Preço da consulta"
          v-model="precoConsulta"
        />
      </div>
      <label for="especialidade" class="form-label"
        >Formas de pagamento da consulta*</label
      >
      <div class="card mb-3">
        <div class="shadow-sm rounded card-header">
          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              value="dinheiro"
              v-model="formaPagamento"
              id="dinheiro"
            />
            <label class="form-check-label px-4" for="dinheiro">
              Em dinheiro
            </label>
          </div>
        </div>
      </div>

      <div class="card mb-3">
        <div class="shadow-sm rounded card-header">
          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              value="pix"
              v-model="formaPagamento"
              id="pix"
            />
            <label class="form-check-label px-4" for="pix"> Pix </label>
          </div>
        </div>
      </div>
      <div class="card mb-3">
        <div class="shadow-sm rounded card-header">
          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              value="cartaoCredito"
              v-model="formaPagamento"
              id="cartaoCredito"
            />
            <label class="form-check-label px-4" for="cartaoCredito">
              Cartão de crédito
            </label>
          </div>
          <div class="px-5 py-4" v-if="cartaoCredito">
            <label class="form-check-label pb-2"> Parcelamento em </label>
            <div class="form-check py-2" id="parcelamento">
              <input
                class="form-check-input"
                type="radio"
                name="numeroParcela"
                id="uma-vez"
                value="1x"
                checked
              />
              <label class="form-check-label" for="uma-vez">
                1x, sem juros
              </label>
            </div>
            <div class="form-check">
              <input
                class="form-check-input"
                type="radio"
                name="numeroParcela"
                id="duas-vezes"
                value="2x"
              />
              <label class="form-check-label" for="duas-vezes">
                2x, sem juros
              </label>
            </div>
            <div class="form-check py-2">
              <input
                class="form-check-input"
                type="radio"
                name="numeroParcela"
                id="tres-vezes"
                value="3x"
              />
              <label class="form-check-label" for="tres-vezes">
                3x, sem juros
              </label>
            </div>
          </div>
        </div>
      </div>
      <div class="progress-status row g-0">
        <div class="progress mb-3 col-10">
          <div
            class="progress-bar bg-primary w-100"
            role="progressbar"
            aria-valuenow="50"
            aria-valuemin="0"
            aria-valuemax="100"
          ></div>
        </div>
        <span class="col-2 text-end text-primary"> 2 de 2 </span>
      </div>
      <button type="button" class="btn btn-primary rounded-pill mb-3 w-100">
        Próximo
      </button>
    </form>
    <div class="col-lg-6 d-none d-lg-block d-xl-block g-0 row">
      <figure class="figure d-flex h-100 align-items-center">
        <img
          src="../assets/desktop-pagina-2.png"
          class="figure-img img-fluid"
          alt="cadastro profisional"
        />
      </figure>
    </div>
  </div>
</template>

<script>
export default {
  name: 'sobre-atendimento',
  data() {
    return {
      formaPagamento: [],
      precoConsulta: '',
      especialidadeSelecionado: '',
      especialidades: [
        'Cardiologia',
        'Dermatologia',
        'Neurologia',
        'Oftalmologia',
        'Psiquiatria',
        'Urologia',
      ],
    }
  },
  computed: {
    preco: function () {
      return this.precoConsulta > 1
    },
    cartaoCredito: function () {
      return this.formaPagamento.includes('cartaoCredito') ? true : false
    },
  },
}
</script>

<style>
.input-group-text {
  background-color: var(--primary-0);
  color: var(--secondary-0);
}
.card {
  border-radius: 10px;
}
</style>
