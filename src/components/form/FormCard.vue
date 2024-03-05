<template>
  <form class="form-container" @submit.prevent="submitForm">
    <label class="paragraph-form">Nome*</label>
    <input type="text" v-model="formData.name" placeholder="Nome e Sobrenome" class="input-form"/>
    <span v-if="invalidName" class="warning-text">O nome deve possuir pelo menos dois caracteres.</span>
    <div class="form-inner">
      <div>
        <label class="paragraph-form">Telefone*</label>
        <input type="text" v-model="formData.phone" v-mask="[phoneMask]" placeholder="(00) 0000[0]-0000" class="input-form" />
        <span v-if="invalidPhone" class="warning-text">O telefone deve ser um número válido.</span>
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
import { mask } from 'vue-the-mask';

export default {
  emits: ['formData'],
  directives: {mask},
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
    phoneMask() {
      const phone = this.formData.phone.replace(/[^0-9]/g, "")?.length;

      if(phone === 11) {
        return "(##) #####-####";
      } else if(phone === 10) {
        return "(##) ####-####"
      } else if(phone === 9) {
        return "#####-####"
      } else {
        return "####-####"
      }
    },
    invalidPhone() {
      return this.formData.phone.length > 0 && this.formData.phone.length <= 8;
    },
    invalidEmail() {
      const regexEmail = /^\w+([.-]?\w+)@\w+([.-]?\w+)(\.\w{2,3})+$/;

      return this.formData.email.length > 0 && !regexEmail.test(this.formData.email);
    },
    formInvalid() {
      return (!this.formData.name.length || this.invalidName) ||
          (!this.formData.email.length || this.invalidEmail) ||
          (!this.formData.phone.length || this.invalidPhone)
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

.warning-text {
  color: #BDBDBD;
  font-family: "Nunito Sans", sans-serif;
  font-weight: 400;
  font-size: 14px;
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

.policy-link {
  color: #FFFFFF;
}

.button-generate {
  width: 100%;
  height: 48px;
  background-color: #F2BF4E;
  font-family: "Nunito Sans", sans-serif;
  font-weight: 800;
  font-size: 16px;
}

.button-generate:hover {
  background-color: #F8DCA0;
}

.icon-arrow-right {
  padding-left: 10px;
}

@media (max-width: 600px) {
  .form-inner {
    display: block;
  }
}
</style>
