<template>
  <div class="navigation">
    <button @click="toggleMenu" class="menu-toggle">
      <i class="fa fa-bars"></i>
    </button>
    <ul :class="{ 'menu-open': isMenuOpen }" class="menu">
      <li v-for="item in menuItems" :key="item.id" class="menu-item">
        <a :href="item.url">{{ item.label }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  data() {
    return {
      isMenuOpen: false,
      menuItems: [
        { id: 1, label: 'Dashboard', url: '/dashboard' },
        { id: 2, label: 'Users', url: '/users' },
        { id: 3, label: 'Products', url: '/products' },
        // Add more menu items as needed
      ]
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    }
  }
};
</script>

<style scoped>
.navigation {
  position: relative;
}

.menu-toggle {
  position: absolute;
  top: 10px;
  left: 10px;
  background: none;
  border: none;
  cursor: pointer;
}

.menu {
  display: none;
  position: absolute;
  top: 40px;
  left: 0;
  background: #f1f1f1;
  padding: 10px;
  list-style: none;
}

.menu-open {
  display: block;
}
</style>
