<template>
  <main>
    <h3>Homee</h3>
    <FormCard @formData="handleFormData" />
    <BusinessCard :dataCard="dataCard" />
  </main>
</template>

<script>
import FormCard from "@/components/form/FormCard.vue";
import BusinessCard from "@/components/card/BusinessCard.vue";

export default {
  components: { FormCard, BusinessCard },
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