<template>
  <div class="card-container">
    <button class="back-button" @click="generateAnotherCard">< Gerar outro cartão</button>
    <div class="card">
      <div class="container">
        <div class="container-img-logo">
          <img src="@/assets/symbol-rd-station-default.svg" alt="lading-page" class="img-logo">
        </div>
        <hr class="hr-line"/>
        <div>
          <p class="paragraph-card">{{ dataCard.name}}</p>
          <p class="paragraph-card">{{  dataCard.phone }}</p>
          <p class="paragraph-card">{{  dataCard.email }}</p>
        </div>
      </div>
    </div>
    <div>
      <button class="download-card-button" :disabled="true">
        <i class="fa-solid fa-down-long icon-download"></i>
        BAIXAR CARTÃO
      </button>
    </div>
    <a href="https://app.rdstation.com.br/signup" target="_blank" class="style-link">
      FAZER UM TESTE GRÁTIS DO RD STATION MARKETING
      <i class="fa-solid fa-right-long icon-arrow-right"></i>
    </a>
  </div>
</template>

<script>
export default {
  emits: ['back'],
  props: {
    dataCard: {
      type: Object,
      required: true
    }
  },
  methods: {
    generateAnotherCard() {
      this.$emit('back');
    }
  }
}
</script>

<style scoped>
.card-container {
  display: flex;
  flex-direction: column;
  gap: 16px;
  width: 510px;
  max-width: 90vw;
  height: 425px;
}

.back-button {
  border: none;
  background-color: inherit;
  cursor: pointer;
  color: #FFFFFF;
  font-family: "Nunito Sans", sans-serif;
  font-weight: 400;
  font-size: 20px;
  text-align: left;
}

.card {
  border-radius: 24px;
  background-color: #FFFFFF;
  display: flex;
  justify-content: center;
  padding: 32px 0;
}

.container{
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  width: 90%;
}

.hr-line {
  height: 75%;
  border-color: #D8D9FD;
  margin: 0;
}

.img-logo {
  width: 70px;
  height: 60px;
}

.paragraph-card {
  font-family: "Nunito Sans", sans-serif;
  font-weight: 400;
  font-size: 20px;
}

.download-card-button {
  width: 100%;
  height: 48px;
  font-family: "Nunito Sans", sans-serif;
  font-weight: 800;
  font-size: 16px;
  background-color: #E1E4E8;
  color: #97A1AC;
}

.style-link {
  font-family: "Nunito Sans", sans-serif;
  font-weight: 800;
  font-size: 16px;
  text-decoration: none;
  color: #FFFFFF;
  text-align: center;
}

.icon-download {
  padding-right: 10px;
}

.icon-arrow-right {
  padding-left: 10px;
}
</style>