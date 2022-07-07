<template>
  <header class="header">
    <div class="logo">Мой ИЖС</div>
    <div class="state">
      <div class="small-g">
        <img width="11" height="11" src="./assets/svg/g.svg" alt="" />
      </div>
      <p class="state-text">Статус</p>
    </div>
  </header>

  <main class="main">
    <div class="info__block">
      <div class="info__block-text">
        Все инженеры и Росреестр за 0 ₽ — оплатите первый этап строительства до
        25 августа и Genius активируется автоматически
      </div>
      <div class="big-g">
        <img width="32" height="32" src="./assets/svg/g.svg" />
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
            :src="require(`./assets/svg/menu/${index + 1}.svg`)"
          />
        </div>
        <div class="menu-item__text">
          {{ menuName }}
        </div>
        <div class="menu-item__arrow">
          <img width="9" height="15" src="./assets/svg/menu/Arrow.svg" />
        </div>
      </div>
    </div>
  </main>

  <footer class="footer">
    <div class="footer-items">
      <div
        class="footer-item"
        v-for="(footerName, index) in footerNames"
        :key="index"
        @click="clickHandler(index)"
        ref="footerItem"
      >
        <img
          class="footer-item__icon"
          width="26"
          height="26"
          :src="activeImg == index ? require(`./assets/svg/footer/${index + 1}active.svg`) : require(`./assets/svg/footer/${index + 1}.svg`)"
        />
        <div class="footer-item__text">{{ footerName }}</div>
      </div>
    </div>
  </footer>
</template>

<script>
import { StatusBar, Style } from '@capacitor/status-bar';
export default {
  name: "App",
  setup() {
    StatusBar.setBackgroundColor({ color: '#F5F5F5' });
    StatusBar.setStyle({style: 	Style.Light})
  },
  data() {
    return {
      activeImg: null,
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
      footerNames: ["Главная", "Каталог", "Landscape", "Стройка", "Меню"],
    };
  },
  mounted(){
    this.activeImg = 0
    this.$refs.footerItem[0].classList.add('active')
  },
  methods: {
    clickHandler(index){
      this.activeImg = index
      for (let i = 0; i < this.$refs.footerItem.length; i++) {
        const el = this.$refs.footerItem[i];
        if (el.classList[1] == 'active'){
          el.classList.remove('active')
        }
      }
      this.$refs.footerItem[index].classList.add('active')
    }
  },
};
</script>

<style>
@import url("@/assets/css/main.css");
/* header */
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
/* main */
.main {
  margin: 40px 20px 0 20px;
}
.info__block {
  display: flex;
  width: 100%;
  height: 107px;
  background: #090909;
  border-radius: 16px;
  color: #F9F9F9;
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
/* footer */
.footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 60px;
  background: #9a989a;
  border-top-right-radius: 16px;
  border-top-left-radius: 16px;
  z-index: 5;
}
.footer-items {
  margin-top: 6px;
  height: 50px;
  justify-content: center;
  display: flex;
}
.footer-item {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 75px;
  height: 100%;
}
.footer-item__text {
  margin-top: 6px;
  font-size: 10px;
  line-height: 100%;
}
.active{
  background: linear-gradient(90deg, #C5ACFF 0%, #FBC2EB 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
</style>
