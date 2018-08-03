<template>
  <div class="layout">
    <header class="header">
      <strong>
        <router-link :to="{ name: 'home' }">Gridsome</router-link>
      </strong>
      <nav class="nav">
        <router-link class="nav__link" :to="{ name: 'home' }">Home</router-link>
        <router-link class="nav__link" :to="{ name: 'about' }">About</router-link>
      </nav>
    </header>
    <slot/>
  </div>
</template>

<style>
body {
  font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif
}
.layout {
  max-width: 600px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}
.header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
}
.nav__link {
  margin-left: 20px;
}
</style>
