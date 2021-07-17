<template>
  <div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group>
        <b-form-row>
          <b-col cols="6"
            ><b-form-input placeholder="Nome" v-model="form.name" required
          /></b-col>
          <b-col
            ><b-form-input
              placeholder="CPF"
              v-model="form.cpf"
              required
              maxlength="11"
          /></b-col>
          <b-col
            ><b-form-input
              placeholder="Data de Nascimento"
              type="date"
              v-model="form.birthdate"
              required
          /></b-col>
        </b-form-row>
      </b-form-group>
      <b-form-group>
        <b-form-row>
          <b-col
            ><b-form-input placeholder="CEP" v-model="form.cep" required
          /></b-col>
          <b-col cols="10"
            ><b-form-input
              placeholder="Endereço"
              v-model="form.address"
              required
          /></b-col>
        </b-form-row>
      </b-form-group>
      <b-form-group>
        <b-form-row>
          <b-col cols="6"
            ><b-form-input placeholder="Complemento" v-model="form.address2"
          /></b-col>
          <b-col
            ><b-form-input placeholder="Cidade" v-model="form.city" required
          /></b-col>
          <b-col
            ><b-form-input placeholder="Estado" v-model="form.state" required
          /></b-col>
        </b-form-row>
      </b-form-group>
      <b-form-group>
        <b-form-row>
          <b-col>
            <b-form-input
              placeholder="Email"
              type="email"
              required
              v-model="form.email"
            />
          </b-col>
          <b-col>
            <b-form-input
              placeholder="Confirmar Email"
              type="email"
              required
              v-model="form.emailcheck"
            />
          </b-col>
        </b-form-row>
      </b-form-group>
      <b-form-group>
        <b-form-row>
          <b-col>
            <b-form-input
              placeholder="Senha"
              type="password"
              required
              v-model="form.password"
            />
          </b-col>
          <b-col>
            <b-form-input
              placeholder="Confirmar Senha"
              type="password"
              required
              v-model="form.passwordcheck"
            />
          </b-col>
        </b-form-row>
      </b-form-group>
      <b-form-group id="input-check" v-slot="{ ariaDescribedby }">
        <b-form-checkbox-group
          v-model="form.checked"
          required
          id="checkboxes"
          :aria-describedby="ariaDescribedby"
        >
          <b-form-checkbox value="yes" class="letter"
            >Eu concordo com a
            <a href="https://boxbrazilplay.tv.br/privacidade.html"
              >Politica de Privacidade</a
            >
            e os Termos de Uso.</b-form-checkbox
          >
        </b-form-checkbox-group>
      </b-form-group>
      <b-button type="submit" variant="primary">Cadastrar</b-button>
      <b-button type="reset" variant="warning">Limpar</b-button>
    </b-form>
    <b-card class="mt-3" header="Form Data Result">
      <pre class="m-0">{{ form }}</pre>
    </b-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: "",
        emailcheck: "",
        password: "",
        passwordcheck: "",
        name: "",
        cpf: "",
        birthdate: "",
        cep: "",
        address: "",
        address2: "",
        state: "",
        city: "",
        checked: [],
      },
      show: true,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.form.email = "";
      this.form.emailcheck = "";
      this.form.password = "";
      this.form.passwordcheck = "";
      this.form.name = "";
      this.form.cpf = "";
      this.form.birthdate = "";
      this.form.cep = "";
      this.form.address = "";
      this.form.address2 = "";
      this.form.state = "";
      this.form.city = "";
      this.form.checked = [];
      // Trick to reset/clear native browser form validation state
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    },
  },
};
</script>

<style>
.letter {
  color: var(--light);
}
</style>