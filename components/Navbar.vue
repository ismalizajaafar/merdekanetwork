<template>
    <nav :class="['navbar', { 'scrolled': isScrolled }]">
      <div class="navbar-container">
        <!-- Logo and Name (Optional) -->
        <img src="@/assets/merdekanetwork.png" class="nav-logo">
        <span class="navbar-name">Merdeka Network</span>
  
        <!-- Hamburger Icon for small screens -->
        <div class="hamburger" @click="toggleMenu" v-if="isMobile">
          <span></span>
          <span></span>
          <span></span>
        </div>
  
        <!-- Menu for large screens or when hamburger is open -->
        <ul class="navbar-menu" :class="{ 'active': isMenuOpen }">
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
  import { ref, onMounted, onUnmounted } from 'vue';
  
  const isScrolled = ref(false);
  const isMenuOpen = ref(false);
  const isMobile = ref(false);
  
  const menus = ref([
    { name: 'Home', link: '/' },
    { name: 'About', link: '/about' },
    { name: 'Services', link: '/Services',
      submenu: [{ name: 'Data Analyst', link: '/services/data'},
                { name: 'Networking Service', link: '/services/network'},
                { name: 'PC Maintenance', link: '/services/pcmaintenance'},
                { name: 'Cloud Storage', link: '/services/cloud'},
              ] 
    },
    { name: 'Career', link: '/career'},
    { name: 'Contact', link: '/contact'},
  ]);
  
  // Scroll event to change navbar style
  const handleScroll = () => {
    isScrolled.value = window.scrollY > 0;
  };
  
  const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value;
  };
  
  const checkMobile = () => {
    isMobile.value = window.innerWidth <= 768; // Adjust based on your preferred breakpoint
  };
  
  onMounted(() => {
    window.addEventListener('scroll', handleScroll);
    window.addEventListener('resize', checkMobile);
    checkMobile(); // Check on page load
  });
  
  onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll);
    window.removeEventListener('resize', checkMobile);
  });
  </script>
  
  <style scoped>
  /* Navbar styles */
  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: #091539;
    transition: background-color 0.3s ease;
    z-index: 1000;
  }
  
  .navbar.scrolled {
    background-color: #091539;
  }
  
  .navbar-container {
    display: flex;
    align-items: center;
    justify-content: space-between; /* Adjusted for space between items */
    /* padding: 15px; */
    padding-top: 5px;
    padding-bottom: 5px;
  }
  
  .nav-logo {
    max-width: 80px;
  }
  .navbar-name {
    font-size: 24px;
    color: #DEE5ED;
    font-weight: bold;
    position: fixed;
    margin-left: 90px;
  }
  
  .navbar-menu {
    display: flex;
    list-style: none;
    justify-content: flex-start;
    margin: 0;
  }
  
  .navbar-item {
    position: relative;
    margin-right: 30px;
  }
  
  .navbar-link {
    color: #DEE5ED;
    font-size: 18px;
    text-decoration: none;
    padding: 5px;
    position: relative;
  }
  
  .navbar-link:hover {
    color: #DEE5ED;
  }
  
  .navbar-item .active {
    color: #DEE5ED;
    font-weight: bold;
  }
  
  /* Dropdown Menu */
  .navbar-item:hover .dropdown, .navbar-item:focus-within .dropdown {
    display: block;
  }
  
  .dropdown {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    background-color: #091539;
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
    color: #DEE5ED;
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
    background-color: #DEE5ED;
  }
  
  /* Hamburger menu (for small screens) */
  .hamburger {
    display: none;
    flex-direction: column;
    cursor: pointer;
  }
  
  .hamburger span {
    width: 25px;
    height: 3px;
    background-color: #DEE5ED;
    margin: 4px 0;
  }
  
  /* For small screens (max width 768px) */
  @media (max-width: 768px) {
    .navbar-menu {
      display: none;
      flex-direction: column;
      width: 100%;
      position: absolute;
      top: 100%;
      left: 0;
      background-color: #091539;
    }
  
    .navbar-menu.active {
      display: flex;
    }
  
    .navbar-item {
      margin-right: 0;
      margin-bottom: 10px;
    }
  
    .hamburger {
      display: flex;
    }
  }
  </style>