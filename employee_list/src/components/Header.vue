<template>
  <header>
    <img
      class="logo"
      src="./icons/vendre-optimizers_logo-black.webp"
      alt="VendreLogo"
    />
    <div id="navbar-links">
      <a href="https://vendre.se/produkt/">PRODUKT</a>
      <a href="https://vendre.se/partners/">PARTNERS</a>
      <a href="https://vendre.se/priser/">PRISER</a>
      <a href="https://vendre.se/referenser/">REFERENSER</a>
      <a href="https://vendre.se/kundcase/">KUNDCASE</a>
      <a href="https://vendre.se/kunskap/">KUNSKAP</a>
    </div>
    <div class="icons">
      <i class="fa-solid fa-globe"></i>
      <i id="hamburger" class="fa-solid fa-bars"></i>
      <button>BOKA BORD</button>
    </div>
  </header>
</template>

<script></script>

<style scoped>
header {
  width: 100%;
  height: calc(34px + 23px * 2);
  background: rgba(255, 255, 255, 0.3);
  backdrop-filter: blur(10px);
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  position: fixed;
}
.logo {
  max-height: var(--space-40);
  width: auto;
}
.icons {
  display: flex;
  height: var(--space-72);
  flex-direction: row;
  align-items: center;
  gap: var(--space-16);
}
#navbar-links {
  display: none;
}
button {
  display: none;
  background-color: var(--color-5);
  padding: var(--space-8) var(--space-16);
}

@media (min-width: 768px) {
  header {
    justify-content: space-between;
  }
  #navbar-links {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: var(--space-16);
  }
  a {
    color: var(--color-5);
    text-decoration: none;
    font-family: Oswald;
  }
  #hamburger {
    display: none;
  }
  button {
    display: block;
  }
}
</style>
