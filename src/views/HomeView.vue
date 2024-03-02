<template>
  <NavBar />
  <div class="content">
    <InitialText />
    <div class="content-center">
      <img src="../assets/img-rd.png" alt="lading-page" class="img-rd">
      <FormCard @formData="handleFormData" />
<!--        <BusinessCard :dataCard="dataCard" />-->
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
      dataCard: {}
    }
  },
  methods: {
    handleFormData(formData) {
      this.dataCard = formData;
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
  height: 100vh;
}

.content-center {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 347px;
  flex-wrap: wrap;
  width: 1281px;
}

.img-rd {
  width: 471px;
  height: 347px;
  margin-top: 14px;
}
</style>