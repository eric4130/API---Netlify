<template>
  <div id="container">

    <nav class="hero is-warning">
      <div class="hero-body" id="navtext">
      <router-link to="/" class="navstyle">Home</router-link>
      <router-link to="/api" class="navstyle">API</router-link>
      </div>
    </nav>

    <section class="section">
      <router-view/>
    </section>

  </div>
</template>

<style lang="scss">
@import '../node_modules/bulma';
@import '/styles/global';
</style>

