<template>
  <div>
    <NavBarTop />
    <NavBarLeft />
    <div class="text-xs sidebar-mini-xs" :class="darkMode ? 'dark-mode' : ''">
      <transition name="fade-slide-rigth" mode="out-in">
        <router-view />
      </transition>
    </div>
    <footer
      class="main-footer text-xs pb-1 pt-1"
      :class="darkMode ? 'dark-mode' : ''"
    >
      <strong>
        © 2021
        <a href="https://soscontingencias.com.co/" target="_blank">
          SOS CONTINGENCIAS
        </a>
      </strong>
      Todos los derechos reservados.
      <div class="float-right d-sm-inline-block">
        <a href="https://soscontingencias.com.co/" target="_blank">
          <img src="img/logo-sos.png" alt="Logo sos" width="100" />
        </a>
      </div>
    </footer>
    <aside class="control-sidebar control-sidebar-dark">
      <!-- Control sidebar content goes here -->
    </aside>
  </div>
</template>
<script>
import NavBarLeft from "@/components/layout/NavBarLeft.vue";
import NavBarTop from "@/components/layout/NavBarTop.vue";
import { ref } from "vue";
export default {
  name: "Home",
  components: {
    NavBarLeft,
    NavBarTop,
  },
  setup() {
    let darkMode = ref(false);

    const darkModeChange = (dato) => {
      console.log(dato);
      darkMode.value = dato;
    };

    return { darkMode, darkModeChange };
  },
};
</script>

<style scoped>
.fade-slide-rigth-enter-active {
  transition: all 0.5s ease;
}
.fade-slide-rigth-leave-active {
  transition: all 0.5s ease;
}
.fade-slide-rigth-enter,
.fade-slide-rigth-leave-to {
  transform: translateX(5%);
  opacity: 0;
}
.bg-sos-blue {
  background: #00529c;
}
.bg-sos-green {
  background: #b0c442;
}
</style>
