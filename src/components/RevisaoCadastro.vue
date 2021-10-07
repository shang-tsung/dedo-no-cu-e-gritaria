<template>
  <div class="container p-5 row">
    <div class="col-sm-12 col-lg-6">
      <h1 class="mb-4">Revisão do cadastro</h1>
      <div class="dadosConfirmacao">
        <label for="Nome"> Nome completo: </label>
        <p>Diogo de Oliveira Santos</p>
        <label for="cpf"> cpf: </label>
        <p>230.000.000.000</p>
        <label for="tel"> telefone: </label>
        <p>(11)555-444</p>
        <label for="state"> Estado </label>
        <p>São Paulo- SP</p>
        <label for="especialidade"> Especialidade </label>
        <p>Paurologista</p>
      </div>
      <div>
        <label for="price"> Preço da consulta </label>
        <p>R$299,99</p>
      </div>
      <div>
        <label for="payment"> forma de pagamento </label>
        <p>Cartão de crédito - Parcelamento em 2x sem juros</p>
      </div>

      <div class="d-flex justify-content-center">
        <button
          type="button"
          class="btn btn-secondary col-4 rounded-pill mb-3 w-100"
        >
          Próximo
        </button>
      </div>
      <div class="d-flex justify-content-center">
        <a href="#" class="text-primary">Editar cadastro</a>
      </div>
    </div>
    <div class="col-lg-6 d-none d-lg-block d-xl-block g-0 row">
      <figure class="figure d-flex h-100 align-items-center">
        <img
          src="../assets/desktop-pagina-3.png"
          class="figure-img img-fluid"
          alt="cadastro profisional"
        />
      </figure>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>

</style>