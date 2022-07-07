<template>
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
          :src="
            activeImg == index
              ? require(`@/assets/svg/footer/${index + 1}active.svg`)
              : require(`@/assets/svg/footer/${index + 1}.svg`)
          "
        />
        <div class="footer-item__text">{{ footerName }}</div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterComponent",
  data() {
    return {
      activeImg: null,
      footerNames: ["Главная", "Каталог", "Landscape", "Стройка", "Меню"],
    };
  },
  mounted() {
    this.activeImg = 0;
    this.$refs.footerItem[0].classList.add("active");
  },
  methods: {
    clickHandler(index) {
      this.activeImg = index;
      for (let i = 0; i < this.$refs.footerItem.length; i++) {
        const el = this.$refs.footerItem[i];
        if (el.classList[1] == "active") {
          el.classList.remove("active");
        }
      }
      this.$refs.footerItem[index].classList.add("active");
    },
  },
};
</script>

<style scoped>
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
.active {
  background: linear-gradient(90deg, #c5acff 0%, #fbc2eb 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
</style>