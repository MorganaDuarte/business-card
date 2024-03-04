<template>
  <form class="form-container" @submit.prevent="submitForm">
    <label class="paragraph-form">Nome*</label>
    <input type="text" v-model="formData.name" placeholder="Nome e Sobrenome" class="input-form"/>
    <span v-if="invalidName" class="warning-text">O nome deve possuir pelo menos dois caracteres.</span>
    <div class="form-inner">
      <div>
        <label class="paragraph-form">Telefone*</label>
        <input type="text" v-model="formData.phone" placeholder="(00) 0000[0]-0000" class="input-form" />
      </div>
      <div>
        <label class="paragraph-form">E-mail*</label>
        <input type="email" v-model="formData.email" placeholder="nome@email.com" class="input-form" />
        <span v-if="invalidEmail" class="warning-text">Deve ser um e-mail válido.</span>
      </div>
    </div>
    <div>
      <ul class="list-style">
        <li class="list-form">Ao preencher o formulário, concordo * em receber comunicações de acordo com meus interesses.</li>
        <li class="list-form">
          Ao informar meus dados, eu concordo com a <a href="https://legal.rdstation.com/pt/privacy-policy/" target="_blank" class="policy-link">Política de privacidade.</a>
        </li>
      </ul>
      <p class="list-form">* Você pode alterar suas permissões de comunicação a qualquer tempo.</p>
    </div>
    <div>
      <button type="submit" class="button-generate" :disabled="formInvalid">
        GERAR CARTÃO GRÁTIS
        <i class="fa-solid fa-right-long icon-arrow-right"></i>
      </button>
    </div>
  </form>
</template>

<script>
export default {
  emits: ['formData'],
  data() {
    return {
      formData: {
        name: '',
        email: '',
        phone: ''
      }
    };
  },
  computed: {
    invalidName() {
      return this.formData.name.length > 0 && this.formData.name.length <= 2;
    },
    invalidEmail() {
      const regex = /^\w+([.-]?\w+)@\w+([.-]?\w+)(\.\w{2,3})+$/;

      return this.formData.email.length > 0 && !regex.test(this.formData.email);
    },
    formInvalid() {
      return (!this.formData.name.length || this.invalidName) ||
          (!this.formData.email.length || this.invalidEmail)
    }
  },
  methods: {
    submitForm() {
      this.$emit('formData', this.formData);
    }
  }
};
</script>

<style scoped>
.form-container{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 620px;
  max-width: 90vw;
}

.paragraph-form {
  color: #FFFFFF;
  font-family: "Nunito Sans", sans-serif;
  font-weight: 700;
  font-size: 14px;
}

.input-form {
  height: 36px;
  width: 100%;
}

.form-inner {
  display: flex;
  gap: 20px;
}

.form-inner div {
  width: 100%;
}

.list-style {
  list-style-position: inside;
  padding-left: 10px;
}

.list-form {
  color: #FFFFFF;
  font-family: "Nunito Sans", sans-serif;
  font-weight: 400;
  font-size: 12px;
}

.button-generate {
  width: 100%;
  height: 48px;
  background-color: #F2BF4E;
  font-family: "Nunito Sans", sans-serif;
  font-weight: 800;
  font-size: 16px;
}

.policy-link {
  color: #FFFFFF;
}

.icon-arrow-right {
  padding-left: 10px;
}

.warning-text {
  color: #FFFFFF;
  font-family: "Nunito Sans", sans-serif;
  font-weight: 400;
  font-size: 12px;
}

@media (max-width: 600px) {
  .form-inner {
    display: block;
  }
}
</style>
