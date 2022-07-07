<template>
  <main class="main">
    <div class="info__block">
      <div class="info__block-text">
        Все инженеры и Росреестр за 0 ₽ — оплатите первый этап строительства до
        25 августа и Genius активируется автоматически
      </div>
      <div class="big-g">
        <img width="32" height="32" src="@/assets/svg/g.svg" />
      </div>
    </div>
    <div class="menu-items">
      <div
        v-for="(menuName, index) in menuNames"
        :key="index"
        class="menu-item"
      >
        <div class="menu-item__icon">
          <img
            width="32"
            height="32"
            :src="require(`@/assets/svg/menu/${index + 1}.svg`)"
          />
        </div>
        <div class="menu-item__text">
          {{ menuName }}
        </div>
        <div class="menu-item__arrow">
          <img width="9" height="15" src="@/assets/svg/menu/Arrow.svg" />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: "MainComponent",
  data() {
    return {
      menuNames: [
        "Как это работает",
        "ИЖС Стандарт",
        "Договоры",
        "Росреестр",
        "Помощь",
        "Промокоды",
        "Партнёрам",
        "Избранное",
      ],
    };
  },
};
</script>

<style scoped>
.main {
  margin: 40px 20px 0 20px;
}
.info__block {
  display: flex;
  width: 100%;
  height: 107px;
  background: #090909;
  border-radius: 16px;
  color: #f9f9f9;
  padding: 16px;
}
.info__block-text {
  font-size: 12.5px;
  line-height: 125%;
  height: 75px;
  margin-right: 16px;
}
.big-g {
  min-width: 64px;
  height: 64px;
  background: linear-gradient(90deg, #c5acff 0%, #fbc2eb 100%);
  display: flex;
  justify-content: center;
  align-items: center;
}
/* menu */
.menu-items {
  margin: 32px 0 68px 0;
}
.menu-item {
  display: flex;
  height: 64px;
  align-items: center;
  border-bottom: 1px solid #e0e0e0;
}
.menu-item__text {
  margin-left: 12px;
}
.menu-item__arrow {
  margin-left: auto;
}
</style>