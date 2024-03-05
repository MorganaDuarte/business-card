<template>
  <NavBar />
  <div class="global-content">
    <TitleText v-if="showForm" />
    <div class="global-content-center">
      <div v-if="isNotCardOnMobile">
        <img src="../assets/img-rd.png" alt="lading-page" class="img-rd">
      </div>
      <FormCard v-if="showForm" @formData="setDataCard" />
      <BusinessCard v-else :dataCard="dataCard" @back="showForm = true" />
    </div>
  </div>
</template>

<script>
import NavBar from "@/components/navBar/NavBar.vue";
import TitleText from "@/components/texts/TitleText.vue";
import FormCard from "@/components/form/FormCard.vue";
import BusinessCard from "@/components/card/BusinessCard.vue";

export default {
  components: { NavBar, TitleText, FormCard, BusinessCard },
  data() {
    return {
      dataCard: {},
      showForm: true
    }
  },
  computed: {
    isNotCardOnMobile() {
      const screenWidth = window.innerWidth;

      return screenWidth > 600 || this.showForm;
    }
  },
  methods: {
    setDataCard(formData) {
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

.global-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: calc(100vh - 84px);
  gap: 44px;
}

.global-content-center {
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
  .global-content {
    height: auto;
    margin-top: 20px;
  }
}
</style>