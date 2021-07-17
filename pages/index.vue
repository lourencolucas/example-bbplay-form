<template>
  <body>
    <b-container class="bv-example-row vh-10">
      <b-row class="text-center">
        <b-col cols="12">
          <b-img src="~/static/boxbrazil-logo.png" style="max-width: 400px"></b-img>
          <h1>BEM-VINDO À BOX BRAZIL PLAY!</h1>
        </b-col>
      </b-row>
      <b-row class="text-center info-b">
        <b-col cols="12">
          Cadastre-se abaixo e tenha acesso aos catálogos disponíveis para
          assinatura.
          <br />
          Ah, não se preocupe. Este cadastro é gratuito!
        </b-col>
      </b-row>
      <b-row class="text-center info-b">
        <b-col cols="12">
          Para conhecer um pouco mais sobre a diversidade da produção
          nacional,<br />
          após conclusão do cadastro, escolha seu plano.
        </b-col>
      </b-row>
      <b-row class="text-center info-b">
        <b-col cols="12">
          Ficou com alguma dúvida?
          <br />
        </b-col>
      </b-row>
      <b-row class="text-center">
        <b-col cols="12">
          <b-button variant="info" href="http://boxbrazilplay.tv.br/">
            CLIQUE AQUI!
          </b-button>
        </b-col>
      </b-row>
      <b-row class="text-center">
        <b-col cols="12"> <h1>CADASTRE-SE GRATUITAMENTE</h1> </b-col>
      </b-row>
      <Cadastro />
      <!-- <Data/> -->
    </b-container>
  </body>
</template>

<script>
export default {};
</script>

<style>
body {
  background-image: url("/bg-form-bbplay.jpg");
  margin: none;
}

.info-b {
  color: var(--light);
}

h1 {
  color: var(--light);
}
</style>