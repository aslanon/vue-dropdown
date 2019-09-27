<template>
  <div id="app">
    {{selected}}
    <div class="container">
      <button @click.stop="isMenu = !isMenu">Menu</button>
      <vue-dropdown
        v-if="isMenu"
        :selectList="menuList"
        @change="e => {selected = e;isMenu = false}"
        @close="isMenu = false"
      ></vue-dropdown>
    </div>
  </div>
</template>

<script>
import VueDropdown from "./components/vue-dropdown.vue";

export default {
  name: "app",
  components: {
    VueDropdown
  },
  data() {
    return {
      selected: null,
      isMenu: false,
      menuList: [
        {
          text: "Vue.js",
          value: 1
        },
        {
          text: "React.js",
          value: 2
        },
        {
          text: "Angular",
          value: 3
        }
      ]
    };
  }
};
</script>

<style lang="scss">
.container {
  position: relative;
}
</style>
