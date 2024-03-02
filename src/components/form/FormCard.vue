<template>
  <div class="container">
    <form>
      <div>
        <p class="paragraph-form">Nome*</p>
        <input type="text" v-model="formData.name" placeholder="Nome e Sobrenome" class="input-form"/>
      </div>
      <div class="form-inner">
        <div>
          <p class="paragraph-form">Telefone*</p>
          <input type="tel" v-model="formData.phone" placeholder="(00) 0 0000-0000" class="input-form" />
        </div>
        <div>
          <p class="paragraph-form">E-mail*</p>
          <input type="email" v-model="formData.email" placeholder="nome@email.com" class="input-form" />
        </div>
      </div>
      <div>
        <ul class="list-style">
          <li class="list-form">Ao preencher o formulário, concordo * em receber comunicações de acordo com meus interesses.</li>
          <li class="list-form">Ao informar meus dados, eu concordo com a Política de privacidade.</li>
        </ul>
        <p class="list-form">* Você pode alterar suas permissões de comunicação a qualquer tempo.</p>
      </div>
      <div>
        <button @click="submitForm" class="button-generate">GERAR CARTÃO GRÁTIS</button>
      </div>
    </form>
  </div>
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
  methods: {
    submitForm() {
      this.$emit('formData', this.formData);
    }
  }
};
</script>

<style scoped>
.container {
  display: inline-flex;
  width: 620px;
  height: 336px;
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
  justify-content: space-between;
}

.list-style {
  padding-left: 25px;
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
</style>
