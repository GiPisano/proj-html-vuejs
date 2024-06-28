<script>
export default {
  data() {
    return {
      events: [
        { text: "CHORAL MUSIC" },
        { text: "CONCERT BAND" },
        { text: "OPERA CONCERTS" },
        { text: "SYMPHONY ORCHESTRA" },
        { text: "FAMILY CONCERTS" },
      ],
      menuOpen: false,
      links: [
        { text: "HOME", svg: null },
        { text: "BLOG", svg: null },
        { text: "EVENTS", svg: "./svg/dropdown.svg" },
        { text: "GALLERY", svg: null },
        { text: "ABOUT US", svg: null },
        { text: "CONTACT US", svg: null },
        { text: "SHOP", svg: null },
      ],
    };
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
    closeMenu() {
      this.menuOpen = false;
    },
  },
};
</script>

<template>
  <header>
    <div class="logo-wrapper">
      <img src="/img/Logo.png" alt="logo" class="logo" />
    </div>
    <nav class="desktop-nav">
      <div class="links">
        <div v-for="link in links">
          <p class="link">
            <div class="svg">
                <a href="#">{{ link.text }}</a>
                <span v-show="link.svg">
                  <img :src="link.svg" alt=""  />
                </span>
            </div>
            <span v-if="link.text === 'EVENTS'" class="dropdown-content">
              <div v-for="event in events" :key="event.text" class="element">
                {{ event.text }}
              </div>
            </span>
          </p>
        </div>
        <img class="search" src="/svg/search.svg" alt="" />
      </div>
    </nav>
    <button class="hamburger" @click="toggleMenu">
      <i class="fa-solid fa-bars"></i>
    </button>

    <div class="menu-overlay" v-show="menuOpen" @click="closeMenu"></div>
    <nav class="mobile-nav" :class="{ open: menuOpen }">
      <div class="links">
        <div v-for="link in links">
          <p class="link">
            <a href="#">{{ link.text }}</a>
            <span v-show="link.svg" class="svg">
              <img :src="link.svg" alt="" />
            </span>
            <span v-if="link.text === 'EVENTS'" class="dropdown-content">
              <div v-for="event in events" :key="event.text" class="element">
                {{ event.text }}
              </div>
            </span>
          </p>
        </div>
        <img class="search" src="/svg/search.svg" alt="" />
      </div>
      <div class="close" @click="closeMenu()">X</div>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss" as *;

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
  background-color: black;
  padding: 20px;

  .logo-wrapper {
    flex: 1;
  }

  .logo {
    color: white;
    width: 120px;
  }

  .desktop-nav {
    display: flex;
    justify-content: flex-start;
    gap: 20px;
    color: white;
  }

  .mobile-nav {
    position: fixed;
    top: 0;
    right: 0;
    width: 80%;
    max-width: 300px;
    height: 100%;
    background-color: #333;
    z-index: 10;
    transform: translateX(100%);
    transition: transform 0.3s ease-out;
    overflow-y: auto;
  }

  .mobile-nav.open {
    transform: translateX(0); // Mostra il menu a tendina quando aperto
  }

  .links {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    padding: 10px;
    .link {
      position: relative;
      a {
        color: white;
        text-decoration: none;
      }
    }
  }

  .search {
    filter: brightness(0) invert(1);
  }

  .menu-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 5;
    display: none;
  }

  .hamburger {
    font-size: 24px;
    background: none;
    border: none;
    color: white;
    cursor: pointer;
    z-index: 10;
    display: none;

    @media (max-width: 768px) {
      display: block;
    }
  }

  .dropdown-content {
    position: absolute;
    top: 100%;
    left: 0%;
    display: none;
    background-color: #fff;
    box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.2);
    z-index: 1;
    background-color: rgb(24, 24, 24);
    min-width: 200px;
    padding: 10px;
    .element {
      cursor: pointer;
      white-space: nowrap;
    }
    .element:hover {
      color: $orange-color;
    }

    
  }

  .link:hover .dropdown-content {
    display: block;
  }

  .links .link a:hover {
    color: $orange-color;
  }

  .close{
    position: absolute;
    top: 5px;
    right: 20px;
    cursor: pointer;
    width: 30px;
    height: 30px;
    border: 1px solid black;
    border-radius: 50%;
    background-color: black;
    display: flex;
    align-items: center;
    justify-content: center
    }

   .close:hover{
        background-color: $orange-color;
    }


  // Media Query per dispositivi mobili
  @media (max-width: 768px) {
    header {
      .mobile-nav {
        padding: 10px;
      }

    }
    .links {
      flex-direction: column;
    }

    .hamburger {
      display: block;
    }

    .menu-overlay {
      display: block;
    }

    .desktop-nav {
      display: none;
    }

    .logo-wrapper {
      flex: initial;
    }
  }
}
</style>
