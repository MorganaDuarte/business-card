<template>
  <nav class="navbar">
    <div class="navbar-content">
      <img src="@/assets/logo-rd-station-default.svg" alt="LogoRD" class="navbar-img" />
      <p>Gerador de Cartão de Visita</p>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  display: flex;
  justify-content: center;
  background-color: #FFFFFF;
  font-size: 24px;
  line-height: 26px;
  font-family: "Darker Grotesque", sans-serif;
  font-weight: 700;
  height: 84px;
  width: 100%;
  box-sizing: border-box;
}

.navbar-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 90vw;
}

.navbar-img {
  width: 147px;
}

@media (max-width: 600px) {
  .navbar {
    font-size: 18px;
    line-height: 19px;
    height: 72px;
  }

  .navbar-img {
    width: 100px;
  }
}
</style>