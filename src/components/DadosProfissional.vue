<template>
  <div class="container-sm p-5 row">
    <form class="col-sm-12 col-lg-6">
      <h1 class="mb-4">Sobre o profisional</h1>
      <h5 class="bold mb-4">Dados do profissional</h5>
      <div class="mb-3 col-12">
        <label for="nomeCompleto" class="form-label">Nome completo*</label>
        <input
          type="text"
          class="form-control"
          id="nomeCompleto"
          v-model="nomeCompleto"
          placeholder="Digite o nome completo"
        />
        erro {{ v$.nomeCompleto.$error }}
        <div class="invalid-feedback">
          Nome obrigatório
        </div>
      </div>
      <div class="mb-3 col-9">
        <label for="cpf" class="form-label">CPF*</label>
        <input
          placeholder="Digite um CPF"
          v-model="cpf"
          type="text"
          class="form-control"
          id="cpf"
        />
        <div class="invalid-feedback">CPF obrigatório</div>
      </div>
      <div class="mb-3 col-9">
        <label for="numero-celular" class="form-label"
          >Número de celular*</label
        >
        <input
          type="text"
          class="form-control"
          id="numero-celular"
          placeholder="(00) 0 0000-0000"
          v-model="telefone"
        />
        <div class="invalid-feedback">Celular obrigatório</div>
      </div>
      <div class="mb-3 row">
        <div class="col">
          <label for="estado" class="form-label">Estado*</label>
          <select
            v-model="estadoSelecionado"
            class="form-select"
            id="estado"
            required
          >
            <option value="" selected disabled>Selecione</option>
            <option
              v-for="(estado, index) in localidades"
              :value="index"
              :key="index"
              :v-model="estadoSelecionado"
            >
              {{ index }}
            </option>
          </select>
        </div>

        <div class="col">
          <label for="cidade" class="form-label">Cidade*</label>
          <select
            class="form-select col-6"
            aria-label="Cidade"
            id="cidade"
            v-model="cidadeSelecionada"
            :disabled="!temEstadoSelecionado"
          >
            <option value="" selected disabled>Selecione</option>
            <option
              v-for="(cidade, index) in cidades"
              :key="index"
              :value="cidade"
            >
              {{ cidade }}
            </option>
          </select>
        </div>
      </div>
      <div class="progress-status row g-0">
        <div class="progress mb-3 col-10">
          <div
            class="progress-bar bg-primary w-50"
            role="progressbar"
            aria-valuenow="50"
            aria-valuemin="0"
            aria-valuemax="100"
          ></div>
        </div>
        <span class="col-2 text-end text-primary"> 1 de 2 </span>
      </div>
      <button type="type" class="btn btn-primary rounded-pill mb-3 w-100">
        Próximo
      </button>
    </form>
    <div class="col-lg-6 d-none d-lg-block d-xl-block g-0 row">
      <figure class="figure d-flex h-100 align-items-center">
        <img
          src="../assets/desktop-pagina-1.png"
          class="figure-img img-fluid"
          alt="cadastro profisional"
        />
      </figure>
    </div>
  </div>
</template>

<script>
import useVuelidate from '@vuelidate/core'
import { required, minLength } from '@vuelidate/validators'

export default {
  name: 'dados-profissional',
  setup() {
    return { v$: useVuelidate() }
  },
  data() {
    return {
      nomeCompleto: '',
      estadoSelecionado: '',
      cidadeSelecionada: '',
      cpf: '',
      telefone: '',
      localidades: {
        Parana: ['londrina', 'Maringa'],
        'Rio Grande do Sul': ['Pelotas', 'Porto Alegre'],
        'Santa Catarina': ['Florianópolis', 'Joinville'],
      },
    }
  },
  computed: {
    temEstadoSelecionado: function() {
      return this.estadoSelecionado != '' ? true : false
    },
    cidades: function() {
      return this.localidades[this.estadoSelecionado]
    },
  },
  validations() {
    return {
      nomeCompleto: {
        required,
        minLength: minLength(15),
      },
    }
  },
}
</script>

<style></style>
