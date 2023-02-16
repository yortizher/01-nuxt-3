<template>
  <nav class="navbar">
  <div class="navbar-brand">
    <a href="#">Brand</a>
  </div>
  <input type="checkbox" id="navbar-toggle" class="navbar-toggle" />
  <label for="navbar-toggle" class="navbar-toggle-label">
    <span></span>
    <span></span>
    <span></span>
  </label>
  <div class="navbar-menu">
    <ul class="navbar-nav">
      <li class="nav-item">
        <a href="#" class="nav-link">Item 1</a>
      </li>
      <li class="nav-item">
        <a href="#" class="nav-link">Item 2</a>
      </li>
      <li class="nav-item">
        <a href="#" class="nav-link">Item 3</a>
      </li>
    </ul>
  </div>
</nav>
</template>
<style scoped>
.navbar {
  background-color: #333;
  color: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1% 1%;
  height: 10vh;
  font-size: 1.7rem;
 
}

.navbar-brand a {
  color: #fff;
  text-decoration: none;
}

.navbar-toggle {
  display: none;
}

.navbar-toggle-label {
  display: block;
  cursor: pointer;
  padding: 5px;
}

.navbar-toggle-label span {
  display: block;
  height: 3px;
  width: 25px;
  background-color: #fff;
  margin: 5px 0;
  transition: all 0.3s ease-in-out;
}

.navbar-menu {
  display: flex;
}

.navbar-nav {
  display: flex;
  margin: 0;
  padding: 0;
}

.nav-item {
  list-style: none;
  margin: 0 10px;
}

.nav-link {
  color: #fff;
  text-decoration: none;
}

@media screen and (max-width: 768px) {
  .navbar-menu {
    position: fixed;
    top: 39px;
    right: -66.66%; /* Cambiado de -100% */
    width: 33.33%; /* Cambiado de 100% */
    height: 100%;
    transition: all 0.3s ease-in-out;
    background-color: #111;
    margin-top: 0;
     z-index: 10;
  }

  .navbar-toggle:checked ~ .navbar-menu {
    right: 0;
  }

  .nav-item {
    width: 100%;
    margin: 10px 0;
    text-align: center;
  }
}

@media screen and (min-width: 768px) {
  .navbar-toggle-label {
    display: none;
  }
}

@media screen and (max-width: 767px) {
  nav ul {
    display: flex;
    flex-direction: column;
    margin: 0;
    padding: 0;
  }

  nav ul li {
    margin: 0;
    padding: 0;
  }

  .navbar-toggle-label {
    display: block;
  }
}

</style>