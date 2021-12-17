<template>
  <div id="wrapper">

    <nav id="navtext">
      <router-link to="/" class="navstyle">Home</router-link>
      <router-link to="/api" class="navstyle">API</router-link>
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
