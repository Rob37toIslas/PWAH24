<template>
  <nav class="navbar">
    <div class="logo">
      <a href="#">MiLogo</a>
    </div>
    <button class="menu-toggle" @click="toggleMenu">
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </button>
    <ul :class="{ 'nav-links': true, 'active': isMenuOpen }">
      <li><a href="#inicio">Inicio</a></li>
      <li><a href="#servicios">Servicios</a></li>
      <li><a href="#contacto">Contacto</a></li>
      <li><a href="#sobre-nosotros">Sobre Nosotros</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
  },
};
</script>

<style scoped>
/* Estilos base */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 1rem;
  background-color: #3d9cbe; /* Color azul preferido */
  color: white;
}

.logo a {
  font-size: 1.5rem;
  text-decoration: none;
  color: white;
  font-weight: bold;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 1rem;
}

.nav-links li a {
  text-decoration: none;
  color: white;
  transition: color 0.3s ease;
}

.nav-links li a:hover {
  color: #f5c518; /* Amarillo al pasar el cursor */
}

/* Botón de menú (pantallas pequeñas) */
.menu-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
  background-color: #3d9cbe;
  border: none;
}

.menu-toggle .bar {
  height: 3px;
  width: 25px;
  background-color: white; /* Cambiado a negro */
  margin: 3px 0;
  transition: all 0.3s ease;
}

/* Media Queries */
@media (max-width: 740px) {
  .nav-links {
    position: absolute;
    top: 20px;
    right: 0;
    background-color: #3d9cbe;
    width: 100%;
    flex-direction: column;
    align-items: center;
    transform: translateY(-200%);
    transition: transform 0.3s ease;
  }

  .nav-links.active {
    transform: translateY(0);
  }

  .menu-toggle {
    display: flex;
  }
}

@media (max-width: 500px) {
  .logo a {
    font-size: 1.2rem;
  }
}

@media (max-width: 420px) {
  .nav-links {
    font-size: 0.9rem;
  }
}
</style>
