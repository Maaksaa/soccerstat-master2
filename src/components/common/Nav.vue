<template>
  <nav class="nav">
    <ul class="nav__list">
      <li class="nav__item">
        <router-link to="/" exact class="nav__link" data-content="Home"
          >Домой</router-link
        >
      </li>
      <li class="nav__item">
        <router-link
          to="/competitions"
          class="nav__link"
          data-content="Competitions"
          >Лиги</router-link
        >
      </li>
      <li class="nav__item">
        <router-link to="/teams" class="nav__link" data-content="Teams"
          >Команды</router-link
        >
      </li>
    </ul>
  </nav>
</template>

<style>
.router-link-exact-active {
  text-decoration: underline;
}
</style>
