<template>
  <div id="nav">
    <!-- vue isikisa ir uzklausa i serveri ir atsiuncia bare bones
    bet reikia naudoti visa sita uzklausa router-link nes kitaip vue.js neisikis
    Taip padaromas psl uzkrovias zymiai greiciau -->
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
    <!-- galima ir sitaip padaryti -->
    <!-- beje sitaip geriau nes jei kazka pakeitem router folder tai cia nereiks keisti nes name tas pats isliks -->
    <!-- <router-link :to="{ name: 'About' }">About</router-link> -->

    <router-link :to="{ name: 'Jobs' }">Jobs</router-link>
  </div>
  <!-- dynamically injected -->

<button @click="redirect">Redirect</button>
<button @click="back">Go back</button>
<button @click="forward">Go forward</button>

  <router-view/>

<!-- tai va maziems projektams geriausia pasilikti tokioje defaul strukturoje, kurti failus views folderyje
 ir prisijungti, bet dar butu gerai kurti ir ten folderius atskiriems faimals kaip contact -->
 <!-- dideliems projektams kurtu atskirus folderius ir juose sudeti psl -->

</template>

<script>
// visada reikia sito po apacia kai naudojam vue ir eksportuojam objektus
export default {
  methods: {
    redirect () {
      // pushing on an extra router
      this.push({ name: 'Home' })
    },
    back () {
      // grizimas atgal i kita psl
      this.$router.go(-1)
    },
    forward () {
      // eina routers po vienu i prieki
      this.$router.go(1)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 10px;
  border-radius: 4px;
}

#nav a.router-link-exact-active {
  color: wheat;
  background: crimson;
}

button {
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 4px;
}
</style>
