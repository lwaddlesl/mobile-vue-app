<template>
<HeaderComponent/>
<MainComponent/>
<FooterComponent/>

</template>

<script>
import { StatusBar, Style } from "@capacitor/status-bar";
import HeaderComponent from "@/components/HeaderComponent.vue";
import MainComponent from "@/components/MainComponent.vue";
import FooterComponent from "@/components/FooterComponent.vue";


export default {
  name: "App",
  components:{
    HeaderComponent,
    MainComponent,
    FooterComponent
  },
  setup() {
    StatusBar.setBackgroundColor({ color: "#F5F5F5" });
    StatusBar.setStyle({ style: Style.Light });
  },
};
</script>

<style>
@import url("@/assets/css/main.css");
</style>
