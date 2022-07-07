<template>
  <header class="header">
    <div class="logo">Мой ИЖС</div>
    <div class="state">
      <div class="small-g">
        <img width="11" height="11" src="@/assets/svg/g.svg" />
      </div>
      <p class="state-text">Статус</p>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
};
</script>

<style scoped>
.header {
  margin: 15px 16px 0 16px;
  display: flex;
  justify-content: space-between;
}
.logo {
  font-size: 26px;
}
.state {
  display: flex;
}
.state-text {
  font-size: 14px;
}
.small-g {
  position: absolute;
  right: 70px;
  display: flex;
  width: 24px;
  height: 24px;
  background: linear-gradient(90deg, #c5acff 0%, #fbc2eb 100%);
  border-radius: 100%;
  justify-content: center;
  margin-right: 8px;
}
.small-g img {
  margin-top: 6px;
}
</style>