<template>
  <form class="row g-3 needs-validation" novalidate>
    <div class="col-md-6">
      <label for="validateName" class="form-label">Nome da Empresa</label>
      <input
        type="text"
        v-model="name"
        class="form-control"
        id="pvalidationCustom01"
        required
      />
      <div class="valid-feedback">Looks good!</div>
    </div>
    <div class="col-md-6">
      <label for="validateCPF" class="form-label">CNPJ</label>
      <input
        type="text"
        v-model="cnpj"
        class="form-control"
        id="pvalidationCustom02"
        required
      />
      <div class="valid-feedback">Looks good!</div>
    </div>
    <div class="col-md-6">
      <label for="validateEmail" class="form-label">E-Mail</label>
      <input
        type="email"
        v-model="email"
        class="form-control"
        id="pvalidationCustom03"
        required
      />
      <div class="invalid-feedback">Please choose a username.</div>
    </div>
    <div class="col-md-6">
      <label for="validationCustom03" class="form-label"
        >Telefone de Contato</label
      >
      <input
        type="text"
        v-model="phone"
        class="form-control"
        id="pvalidationCustom04"
        required
      />
      <div class="invalid-feedback">Please provide a valid city.</div>
    </div>
    <div class="col-md-6">
      <label for="validationCustom04" class="form-label">Senha</label>
      <input
        type="password"
        v-model="password"
        class="form-control"
        id="pvalidationCustom05"
        required
      />
      <div class="invalid-feedback">Please select a valid state.</div>
    </div>
    <div class="col-md-6">
      <label for="validationCustom05" class="form-label">Confirmar Senha</label>
      <input
        type="password"
        v-model="validatePassword"
        class="form-control"
        id="pvalidationCustom06"
        required
      />
      <div class="invalid-feedback">Please provide a valid zip.</div>
    </div>
    <div class="col-12">
      <div class="form-check">
        <input
          class="form-check-input"
          v-model="agreement"
          type="checkbox"
          id="pinvalidCheck"
          required
        />
        <label class="form-check-label" for="invalidCheck">
          Li e estou de acordo com os termos.
        </label>
        <div class="invalid-feedback">You must agree before submitting.</div>
      </div>
    </div>
    <div class="col-12">
      <button class="btn btn-primary" type="submit">Confirmar</button>
    </div>
  </form>
</template>

<script>
export default {
  name: "SignUpPartner",
  data() {
    return {
      form: {
        enterpriseName: "",
        cnpj: "",
        email: "",
        phone: "",
        password: "",
        validatePassword: "",
        agreement: "",
      },
    };
  },
  methods: {
    addUser() {
      this.$store.dispatch("commitUser", {
        name: this.form.enterpriseName,
        cnpj: this.form.cnpj,
        email: this.form.email,
        phone: this.form.phone,
        password: this.form.password,
        agreement: this.form.agreement,
      });
      this.$router.push("/login");
    },
  },
};
</script>