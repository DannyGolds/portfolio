<template>
    <header class="header">
      <div class="container">
        <div class="header__inner">
          <ul class="header__list" :class="{'header__list--active': burgerState}">
            <li class="header__item" v-for="link in links" :key="link">
              <a :href="link.address" :class="link.class" class="header__link tr" @click="hideMenu()"> {{ link.text }} </a>
            </li>
          </ul>
          <div class="header__burger" :class="{'header__burger--active': burgerState}" @click="showMenu()">
            <span></span>
          </div>
        </div>
      </div>
    </header>
</template>

<script>
export default {
  name: 'AppHeader',
  data() {
    return {
      links: [
        {
          text: 'Главная',
          address: '#',
          class: 'header__link--active'
        },
        {
          text: 'Обо мне',
          address: '#about',
          class: ''
        },
        {
          text: 'Мои навыки',
          address: '#skills',
          class: ''
        },
        {
          text: 'Проекты',
          address: '#portfolio',
          class: ''
        },
        {
          text: 'Контакты',
          address: '#contacts',
          class: ''
        },
      ],
      burgerState: false,
    }
  },
  methods: {
    showMenu() {
      this.burgerState == false ? this.burgerState = true : this.burgerState = false
    },
    hideMenu() {
      if(this.burgerState) {
        this.burgerState = false
      } else {
        this.burgerState += ''
      }
    }
  }
}
</script>

<style>
</style>