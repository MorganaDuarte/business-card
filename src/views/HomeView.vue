<template>
  <main class="app-container">
    <NavBar />
    <div>
      <span>Gerador de Cartão de Visita</span>
    </div>
    <FormCard @formData="handleFormData" />
    <BusinessCard :dataCard="dataCard" />
  </main>
</template>

<script>
import NavBar from "@/components/navBar/NavBar.vue";
import FormCard from "@/components/form/FormCard.vue";
import BusinessCard from "@/components/card/BusinessCard.vue";

export default {
  components: { NavBar, FormCard, BusinessCard },
  data() {
    return {
      dataCard: {}
    }
  },
  methods: {
    handleFormData(formData) {
      this.dataCard = formData
    }
  }
}
</script>

<style>
body {
  margin: 0;
  background-color: #806EFF;
}
.app-container {
  padding-top: 84px;
}
</style>