<template>
  <form>
    <label class="paragraph-form">Nome*</label>
    <input type="text" v-model="formData.name" placeholder="Nome e Sobrenome" class="input-form"/>
    <div class="form-inner">
      <div>
        <label class="paragraph-form">Telefone*</label>
        <input type="tel" v-model="formData.phone" placeholder="(00) 0 0000-0000" class="input-form" />
      </div>
      <div>
        <label class="paragraph-form">E-mail*</label>
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
  flex-wrap: wrap;
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
