<template>
  <footer class="footer" id="contacts">
    <div class="container">
      <div class="footer__inner">
        <h2 class="footer__title title">Контакты</h2>
        <p class="footer__text text">
          Хотите заказать проект или узнать какие-либо детали? Смело спрашивайте о чем-либо и отправляйте форму!
        </p>
        <form action="" class="footer__form">
          
          <input id="input1" placeholder="Ваше имя" type="text" class="footer__form-input" v-model="name">
          <input id="input2" placeholder="Ваша почта(пример: example@gmail.com)" type="text" class="footer__form-input" v-model="email">
          <textarea name="id" placeholder="Ваше сообщение" class="footer__form-text" style="resize: none" v-model="text"></textarea>
        </form>
        <button class="footer__btn" @click="showSended()">
          Написать соообщение
        </button>
        <div class="footer__networks">
          <a class="social__network" :href="social.address" v-for="social in socials" :key="social" target="_blank"> <img class="social__network-img" :src="social.img"> </a>
        </div>
        <p class="footer__postscriptum">
          Подписывайтесь на мои социальные сети в instagram, vk, facebook, discord
        </p>
      </div>
    </div>
    <div :class="{'sended--active': message}" class="sended">
      <p class="sended__text text">Форма успешно отправлена!</p>
    </div>
    <div :class="{'sended--isnt': notCorrect}" class="notSended">
      <p class="sended__text text">Форма некорректна!</p>
    </div>
  </footer>
</template>

<script>
export default {
    name: 'AppFooter',
    data() {
      return {
        socials: [
          {
            img: require('../assets/icons/instagram.svg'),
            address: 'https://www.instagram.com/'
          },
          {
            img: require('../assets/icons/vk.svg'),
            address: 'https://vk.com/dannygolds'
          },
          {
            img: require('../assets/icons/ds.svg'),
            address: 'https://discord.com/channels/Danny Golds#5428'
          },
          {
            img: require('../assets/icons/facebook.svg'),
            address: 'https://www.facebook.com/'
          },
        ],
        btnState: false,
        message: false,
        notCorrect: false,
        inputs: [
          {
            placeholder: 'Введите ваше имя'
          },
          {
            placeholder: 'Введите ваш e-mail для связи'
          }
        ],
        name: '',
        email: '',
        text: ''
      }
    },
    methods: {
      showSended() {
        if(this.name == '' || this.email == '' || this.text == '') {
          this.notCorrect = true
        } else if(this.name !== '' && this.email !== '' && this.text !== ''){
          this.message = true
          this.name = ''
          this.email = ''
          this.text = ''
        }

        setTimeout(() => {
          if(this.message == true) {
            this.message = false
          } else if(this.notCorrect == true) {
            this.notCorrect = false
          }
        }, 3000)
      }
    }
}
</script>
