<template>
  <body>
    <b-container class="bv-example-row vh-10">
      <b-row class="text-center">
        <b-col cols="12">
          <b-img
            src="https://res.cloudinary.com/lourencolucas/image/upload/v1626720232/BB-PLAY/boxbrazil-logo_nyjito.png"
            fluid
            alt="Responsive image"
          ></b-img>
          <h1 class="m-3">BEM-VINDO À BOX BRAZIL PLAY!</h1>
        </b-col>
      </b-row>
      <b-row class="text-center info-b">
        <b-col cols="12" class="m-1">
          Cadastre-se abaixo e tenha acesso aos catálogos disponíveis para
          assinatura.
        </b-col>
      </b-row>
      <b-row class="text-center info-b">
        <b-col cols="12">
          Ah, não se preocupe. Este cadastro é gratuito!
        </b-col>
      </b-row>
      <b-row class="text-center info-b">
        <b-col cols="12 m-1">
          Para conhecer um pouco mais sobre a diversidade da produção nacional,
          após conclusão do cadastro, escolha seu plano.
        </b-col>
      </b-row>
      <b-row class="text-center info-b m-3">
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
        <b-col cols="12">
          <h2 class="m-5">CADASTRE-SE GRATUITAMENTE</h2>
        </b-col>
      </b-row>
      <Cadastro />
    </b-container>
  </body>
</template>

<script>
export default {};
</script>

<style>
body {
  background-image: url("https://res.cloudinary.com/lourencolucas/image/upload/v1626720232/BB-PLAY/bg-form-bbplay_vsvvg8.jpg");
  /* margin: none; */
}

.info-b {
  color: var(--light);
}

h1 {
  color: var(--light);
}

h2 {
  color: var(--light);
}
</style>
