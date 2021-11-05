<template>
  <div id="app">
    <header class="header">
      <nav class="nav">
        <div class="nav__brand">
          Yandex Map WebAPI
        </div>
      </nav>
    </header>
    <div id="content">
      <map-view/>
    </div>
  </div>
</template>

<script>
import MapView from "./components/MapView";
export default {
  name: 'App',
  components: {
    MapView,
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Zen+Maru+Gothic:wght@300;400;500;700;900&display=swap');

* {
  margin: 0;
  padding: 0;
}

#app {
  font-family: 'Zen Maru Gothic', sans-serif;
}

.nav {
  width: 100%;
  display: inline-flex;
  justify-content: center;
  background: #DBFF76;
  &__brand {
    color: #2D2D2D;
    padding: 10px 0;
  }
}
</style>
