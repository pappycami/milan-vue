<template>
  <header>
    <slot name="header" />
  </header>
  <main>
    <slot />
  </main>
</template>

<style scoped>
header {
  background: #35495e;
  color: white;
  padding: 1rem;
}
main {
  padding: 1rem;
}
</style>
