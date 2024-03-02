<template>
  <nav class="navbar">
    <div class="navbar-left">
      <img src="@/assets/logo-rd-station-default.svg" alt="LogoRD" />
    </div>
    <div>
      <p>Gerador de Cartão de Visita</p>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #FFFFFF;
  font-size: 24px;
  line-height: 26px;
  font-family: "Darker Grotesque", sans-serif;
  font-weight: 700;
  height: 84px;
  padding: 24px 80px 24px 80px;
  width: 100%;
  position: fixed;
  top: 0;
  box-sizing: border-box;
}

.navbar-left img {
  width: 147px;
}

@media (max-width: 590px) {
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #FFFFFF;
    font-size: 18px;
    line-height: 19px;
    font-family: "Darker Grotesque", sans-serif;
    font-weight: 700;
    height: 72px;
    padding: 24px 20px 24px 20px;
    width: 100%;
    position: fixed;
  }

  .navbar-left img {
    width: 100px;
  }
}
</style>