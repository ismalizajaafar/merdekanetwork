<template>
  <div>
    <nav class="uk-navbar-container uk-navbar-transparent" uk-navbar>
      <div class="uk-navbar-left">
        <a href="/" class="uk-navbar-item uk-logo">Merdeka Network</a>
      </div>
      <div class="uk-navbar-right">
        <ul class="uk-navbar-nav">
          <li><a href="/">Home</a></li>
          <li><a href="/about">About</a></li>
          <li><a href="/services">Services</a></li>
          <li><a href="/career">Career</a></li>
          <li><a href="/contact">Contact</a></li>
        </ul>
      </div>
    </nav>
    <NuxtPage />
    <footer class="uk-section uk-section-small uk-section-secondary uk-light uk-text-center">
      <p>&copy; 2024 Merdeka Network. All rights reserved.</p>
    </footer>
  </div>
</template>
