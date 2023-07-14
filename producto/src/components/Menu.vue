<template>
    <div>
    <nav class="black">
      <div class="nav-wrapper">
        <a href="#!" class="brand-logo"></a>
        <a href="#" data-target="mobile-demo" class="sidenav-trigger"><i class="material-icons">menu</i></a>
        <ul class="left hide-on-med-and-down">
          <li><router-link to="/">MegaDron</router-link></li>
          <li><router-link to="/">Inicio</router-link></li>
          <li><router-link to="/tienda">Tienda</router-link></li>
        </ul>
      </div>
    </nav>
    <ul class="sidenav" id="mobile-demo">
      <li><router-link to="/">MegaDron</router-link></li>
      <li><router-link to="/">Inicio</router-link></li>
      <li><router-link to="/tienda">Tienda</router-link></li>
    </ul>
    <routerView/>
  </div>
  </template>
  
  <style lang="scss">
  #app {
  font-family: 'Times New Roman', Times, serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #000000;
  }
  </style>
  
<script>
export default {
  name: 'Menu',
  props: {

  }
}
</script>