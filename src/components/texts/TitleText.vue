<template>
  <div class="card">
    <h1 class="title">Gerador de Cartão de Visita</h1>
    <h2 class="subtitle">
      Crie grátis seu cartão de visita em passos rápidos! Você o insere no Instagram e demais canais digitais.
    </h2>
  </div>
</template>

<style scoped>
.card {
  width: 90vw;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-content: center;
  justify-content: center;
}

.title {
  color: #FFFFFF;
  font-family: "Red Hat Display", sans-serif;
  font-weight: 700;
  font-size: 40px;
  text-align: center;
  margin: 0;
}

.subtitle {
  color: #FFFFFF;
  font-family: "Nunito Sans", sans-serif;
  font-weight: 400;
  font-size: 20px;
  max-width: 621px;
  text-align: center;
}

@media (max-width: 600px) {
  .title {
    font-size: 24px;
  }

  .subtitle {
    font-size: 16px;
  }
}
</style>
