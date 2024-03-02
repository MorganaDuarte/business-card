<template>
  <form @submit.prevent="submitForm">
    <div class="form-group">
      <label for="name">Nome:</label>
      <input type="text" id="name" v-model="formData.name">
    </div>
    <div class="form-group">
      <div class="form-group-inner">
        <label for="email">E-mail:</label>
        <input type="email" id="email" v-model="formData.email">
      </div>
      <div class="form-group-inner">
        <label for="phone">Telefone:</label>
        <input type="tel" id="phone" v-model="formData.phone">
      </div>
    </div>
    <div class="form-group">
      <button type="submit">Enviar</button>
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

<style>
.form-group {
  margin-bottom: 15px;
  display: flex;
  justify-content: space-between;
}

.form-group-inner {
  width: calc(50% - 5px);
}

.form-group label {
  display: block;
  margin-bottom: 5px;
}

.form-group input {
  width: 100%;
  padding: 5px;
}

.form-group button {
  width: auto;
  cursor: pointer;
}
</style>
