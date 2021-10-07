<template>
  <div class="container">
    <div class="card">
     <DadosProfissional/>
     <!-- <Atendimento/>  -->
    <!--<RevisaoCadastro /> -->
    </div>
  </div>
</template>

<script>
import DadosProfissional from "@/components/DadosProfissional";
//import Atendimento from "@/components/Atendimento";
//import RevisaoCadastro from "@/components/RevisaoCadastro";
export default {
  name: "Cadastro",
  components: {
    DadosProfissional,
    //Atendimento,
    //RevisaoCadastro
  },
};
</script>

<style>
.container > .card {
  border-top-left-radius: 25px;
  border-top-right-radius: 25px;
}
@media (min-width: 992px) {
  .container{
    max-width: 936px;
  }
  .container > .card {
    border-bottom-left-radius: 25px;
    border-bottom-right-radius: 25px;
  }
}
.card-title {
  font-family: "Comfortaa", cursive;
}


</style>