<template>
  <div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group>
        <b-form-row>
          <b-col cols="6">
            <label for="input-1">Nome completo:</label>
            <b-form-input
              id="input-1"
              placeholder="José da Silva"
              v-model="form.name"
              required
            />
          </b-col>
          <b-col>
            <label for="input-2">CPF:</label>
            <b-form-input
              placeholder="000.000.000-00"
              v-model="form.cpf"
              required
              maxlength="14"
              id="input-2"
              v-mask="'###.###.###-##'"
          /></b-col>
        </b-form-row>
      </b-form-group>
      <b-form-group>
        <b-form-row>
          <b-col cols="6">
            <label for="input-3">Data de Nascimento:</label>
            <b-form-input
              type="text"
              v-model="form.birthdate"
              required
              id="input-3"
              v-mask="'##-##-####'"
              placeholder="01-01-2000"
            />
          </b-col>
          <b-col cols="2">
            <label for="input-13">DDD:</label>
            <b-form-input
              placeholder="00"
              v-model="form.ddd"
              required
              maxlength="2"
              id="input-13"
          /></b-col>
          <b-col>
            <label for="input-14">Telefone:</label>
            <b-form-input
              placeholder="00000-0000"
              v-model="form.phone"
              required
              maxlength="10"
              id="input-14"
              v-mask="'#####-####'"
          /></b-col>
        </b-form-row>
      </b-form-group>
      <b-form-group>
        <b-form-row>
          <b-col>
            <label for="input-4">CEP:</label>
            <b-form-input
              placeholder="00000-000"
              v-model="form.cep"
              required
              id="input-4"
              v-mask="'#####-###'"
              @keyup="fetchCep()"
          /></b-col>
          <b-col cols="9">
            <label for="input-5">Endereço:</label>
            <b-form-input
              placeholder="R. José do Carmo Oliveira, 170"
              v-model="form.address"
              required
              id="input-5"
          /></b-col>
        </b-form-row>
      </b-form-group>
      <b-form-group>
        <b-form-row>
          <b-col cols="6">
            <label for="input-6">Complemento:</label>
            <b-form-input
              placeholder="Apt 02"
              v-model="form.address2"
              id="input-6"
          /></b-col>
          <b-col>
            <label for="input-7">Cidade:</label>
            <b-form-input
              placeholder="Porto Alegre"
              v-model="form.city"
              required
              id="input-7"
          /></b-col>
          <b-col>
            <label for="input-8">Estado:</label>
            <b-form-input
              placeholder="Rio Grande do Sul"
              v-model="form.state"
              required
              id="input-8"
          /></b-col>
        </b-form-row>
      </b-form-group>
      <b-form-group>
        <b-form-row>
          <b-col>
            <label for="input-9">Email:</label>
            <b-form-input
              placeholder="jose@meuemail.com"
              type="email"
              required
              v-model="form.email"
              id="input-9"
            />
          </b-col>
          <b-col>
            <label for="input-10">Confirmar Email:</label>
            <b-form-input
              placeholder="jose@meuemail.com"
              type="email"
              required
              v-model="form.emailcheck"
              id="input-10"
              :state="validation"
            />
            <b-form-invalid-feedback :state="validation">
              Os emails precisam ser iguais.
            </b-form-invalid-feedback>
          </b-col>
        </b-form-row>
      </b-form-group>
      <b-form-group>
        <b-form-row>
          <b-col>
            <label for="input-11">Senha:</label>
            <b-form-input
              type="password"
              placeholder="********"
              required
              v-model="form.password"
              id="input-11"
            />
          </b-col>
          <b-col>
            <label for="input-12">Confirmar Senha:</label>
            <b-form-input
              type="password"
              placeholder="********"
              required
              v-model="form.passwordcheck"
              id="input-12"
              :state="validationPassword"
            />
            <b-form-invalid-feedback :state="validationPassword">
              As senhas precisam ser iguais e conter 8 ou mais caracteres.
            </b-form-invalid-feedback>
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
            e os Termos de uso.</b-form-checkbox
          >
        </b-form-checkbox-group>
      </b-form-group>
      <b-button type="submit" variant="primary">Cadastrar</b-button>
      <b-button type="reset" variant="warning">Limpar</b-button>
    </b-form>
    <b-card class="m-3" header="Form Data Result">
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
        ddd: "",
        phone: "",
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
      if (
        this.form.email != this.form.emailcheck ||
        this.form.password != this.form.passwordcheck
      ) {
        alert("Email ou senha não conferem!");
      } else {
        alert(JSON.stringify(this.form));
      }
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
      this.form.ddd = "";
      this.form.phone = "";
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
    async fetchCep() {
      if (this.form.cep.length == 9) {
        const ip = await this.$axios.$get(
          "https://brasilapi.com.br/api/cep/v2/" + this.form.cep
        );
        this.form.address = ip.street + " - " + ip.neighborhood;
        this.form.state = ip.state;
        this.form.city = ip.city;
      }
    },
  },
  computed: {
    validation() {
      return (
        this.form.email == this.form.emailcheck && this.form.email.length > 0
      );
    },
    validationPassword() {
      return (
        this.form.password === this.form.passwordcheck &&
        this.form.password.length >= 8
      );
    },
  },
};
</script>

<style>
.letter {
  color: var(--light);
}
label {
  color: var(--light);
}
</style>
