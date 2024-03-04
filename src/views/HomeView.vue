<template>
  <NavBar />
  <div class="content">
    <InitialText v-if="showForm" />
    <div class="content-center">
      <div v-if="isNotCardOnMobile">
        <img src="../assets/img-rd.png" alt="lading-page" class="img-rd">
      </div>
      <FormCard v-if="showForm" @formData="handleFormData" />
      <BusinessCard v-else :dataCard="dataCard" @back="showForm = true" />
    </div>
  </div>
</template>

<script>
import NavBar from "@/components/navBar/NavBar.vue";
import InitialText from "@/components/texts/InitialText.vue";
import FormCard from "@/components/form/FormCard.vue";
import BusinessCard from "@/components/card/BusinessCard.vue";

export default {
  components: { NavBar, InitialText, FormCard, BusinessCard },
  data() {
    return {
      dataCard: {},
      showForm: true
    }
  },
  computed: {
    isNotCardOnMobile() {
      const screenWidth = window.innerWidth;
      console.log(screenWidth)

      return screenWidth > 600 || this.showForm;
    }
  },
  methods: {
    handleFormData(formData) {
      this.dataCard = formData;
      this.showForm = false;
    }
  }
}
</script>

<style>
body {
  margin: 0;
  background-image: linear-gradient(to right, #6C5AE0, #806EFF);
}

.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: calc(100vh - 84px);
  gap: 44px;
}

.content-center {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  max-width: 1280px;
  width: 90vw;
  column-gap: 100px;
}

.img-rd {
  max-width: 75vw;
}

@media (max-width: 600px) {
  .content {
    height: auto;
    margin-top: 20px;
  }
}
</style>