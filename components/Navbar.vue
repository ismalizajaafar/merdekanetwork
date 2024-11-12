<template>
  <nav :class="['navbar', { 'scrolled': isScrolled }]">
    <div class="navbar-container">
      <!-- Logo and Name (Optional) -->
      <span class="navbar-name">Merdeka Network</span>

      <ul class="navbar-menu">
        <li class="navbar-item" v-for="menu in menus" :key="menu.name">
          <NuxtLink 
            :to="menu.link" 
            class="navbar-link"
            :exact-active-class="'active'"
            exact
          >
            {{ menu.name }}
          </NuxtLink>

          <!-- Dropdown Menu -->
          <ul v-if="menu.submenu" class="dropdown">
            <li v-for="submenu in menu.submenu" :key="submenu.name">
              <NuxtLink 
                :to="submenu.link" 
                :exact-active-class="'active'"
                exact
              >
                {{ submenu.name }}
              </NuxtLink>
            </li>
          </ul>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
// Scroll handling and menu data
import { ref, onMounted, onUnmounted } from 'vue';

const isScrolled = ref(false);
const menus = ref([
  { name: 'Home', link: '/' },
  { name: 'About', link: '/about' },
  { name: 'Services', link: '/Services',
   submenu: [{ name: 'Data Analyst', link: '/services/data'},
             { name: 'Networking Service', link: '/services/network'},
             { name: 'PC Maintenance', link: '/services/pcmaintenance'},
             { name: 'Cloud Storage', link: '/services/cloud'},
            ]  },
  { name: 'Career', link: '/career'},
  { name: 'Contact', link: '/contact'},
]);

// Scroll event to change navbar style
const handleScroll = () => {
  isScrolled.value = window.scrollY > 0;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
/* Navbar styles */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: rgba(0, 0, 0, 0); /* Transparent */
  transition: background-color 0.3s ease;
  z-index: 1000;
}

.navbar.scrolled {
  background-color: rgba(255, 255, 255, 0.9); /* Light background on scroll */
}

.navbar-container {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 15px;
}

.navbar-name {
  font-size: 24px;
  color: #4B9B9B; /* Soft teal */
  font-weight: bold;
}

.navbar-menu {
  display: flex;
  list-style: none;
  margin-left: 20px;
}

.navbar-item {
  position: relative;
  margin-right: 30px;
}

.navbar-link {
  color: #4B9B9B; /* Soft teal */
  font-size: 18px;
  text-decoration: none;
  padding: 5px;
  position: relative;
}

.navbar-link:hover {
  color: #A0D6D6; /* Lighter teal on hover */
}

.navbar-item .active {
  color: #A0D6D6; /* Lighter teal for active links */
  font-weight: bold;
}

/* Dropdown Menu */
.navbar-item:hover .dropdown, .navbar-item:focus-within .dropdown {
  display: block;
}

/* Remove bullets from the dropdown menu */
.dropdown {
  display: none;
  position: absolute;
  top: 100%;
  left: 0;
  background-color: white;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  min-width: 150px;
  padding: 0;
  margin: 0;
}

.dropdown li {
  list-style-type: none;
  padding: 10px;
}

.dropdown li a {
  color: #4B9B9B; /* Soft teal */
  text-decoration: none;
}

.navbar-item a {
  display: block;
  position: relative;
  padding-bottom: 5px;
}

.navbar-item a::after {
  content: '';
  display: block;
  width: 100%;
  height: 2px;
  background-color: transparent;
  transition: width 0.3s ease, background-color 0.3s ease;
}

.navbar-item a:hover::after {
  background-color: #A0D6D6; /* Light teal underline on hover */
}
</style>
