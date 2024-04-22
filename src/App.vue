<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/new">Create new  </RouterLink>
    </nav>
  </header>
  <main>
    <RouterView />
  </main>
</template>

<style scoped>
nav{
  font-family: cursive;
  display: flex;
  justify-content: space-evenly;
  width:15vw;
  min-width: 15em;
  height: 2.5em;
}
a{
  text-decoration: none;
  color: limegreen;
}
a:hover{
  text-decoration: dotted;
  text-decoration-color: currentColor;
  color:forestgreen;
}
main{
  font-family: cursive;
  background-color: lightgreen;
  height: calc(100vh - 2em);
  margin: -8px;
  padding-top: 1em;
}
</style>
