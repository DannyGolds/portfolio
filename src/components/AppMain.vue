<template>
  <main class="main">
    <section class="home" id="home">
      <div class="container">
        <div class="home__inner">
          <transition name="info">
            <div class="home__content">
              <h2 class="home__person">{{ name }}</h2>
              <p class="home__info">
                Front-end разработчик | {{ years }} лет, Выкса
              </p>
            </div>
          </transition>
          <img class="home__img" src="../assets/imgs/me.webp" alt="myself me" />
        </div>
      </div>
    </section>
    <section class="about" id="about">
      <div class="container">
        <div class="about__inner">
          <h2 class="about__title title">Обо мне</h2>
          <p class="about__text">
            Здравствуйте, я Даниил - фронтенд разработчик из России. Я увлекаюсь
            дизайном различных проектов, ну а главная моя деятельность - это
            разработка веб-приложений и сайтов. Когда я начал изучать профессию
            веб-разработчик, первым моим курсом был "веб-разработчик" от
            компании Яндекс. В последствии я начал увлекаться чтением различных
            библиотек и книг, как в интернете, так и настольных вариантов.
            Всегда готов к работе с хорошей компанией. Все мои недостатки я
            выслушиваю и понимаю, где надо что-то исправить. Сам по себе я очень
            дружелюбный и в то же время ответственный человек, стараюсь
            выполнять все задачи в поставленный срок.
          </p>
        </div>
      </div>
    </section>
    <section class="skills" id="skills">
      <div class="container">
        <div class="skills__inner">
          <h2 class="skills__title title">Мои навыки</h2>
          <p class="skills__text text">
            Я работаю с такими фреймворками и программами как
          </p>
          <div class="skills__content">
            <div class="skills__item" v-for="skill in skills" :key="skill">
              <img class="skills__icon" :src="skill.img" height="90" />
              <p class="skills__description">{{ skill.text }}</p>
              <progress
                class="skills__progress"
                min="0"
                max="100"
                :value="skill.progress"
              ></progress>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="portfolio" id="portfolio">
      <div class="container">
        <div class="portfolio__inner">
          <h2 class="portfolio__title title">Проекты</h2>
          <div class="portfolio__card" v-for="work in works" :key="work">
            <img class="portfolio__img" :src="work.img" />
            <a class="portfolio__link" :title="work.desc" :href="work.address">
              {{ work.text }}
            </a>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: 'AppMain',
  data() {
    return {
      skills: [
        {
          img: require('../assets/icons/ap.svg'),
          text: 'Adobe Photoshop',
          progress: '40',
        },
        {
          img: require('../assets/icons/ai.svg'),
          text: 'Adobe Illustrator',
          progress: '20',
        },
        {
          img: require('../assets/icons/ae.svg'),
          text: 'Adobe After Effects',
          progress: '20',
        },
        {
          img: require('../assets/icons/fig.svg'),
          text: 'Figma',
          progress: '90',
        },
        {
          img: require('../assets/icons/gulp.svg'),
          text: 'Gulp',
          progress: '100',
        },
        {
          img: require('../assets/icons/js.svg'),
          text: 'Vue JS',
          progress: '60',
        },
        {
          img: require('../assets/icons/js.svg'),
          text: 'React JS',
          progress: '30',
        },
        {
          img: require('../assets/icons/css.svg'),
          text: 'CSS3',
          progress: '100',
        },
        {
          img: require('../assets/icons/js.svg'),
          text: 'JavaScript',
          progress: '90',
        },
        {
          img: require('../assets/icons/html.svg'),
          text: 'HTML',
          progress: '95',
        },
      ],
      works: [
        {
          img: require('../assets/imgs/portfolio-1.webp'),
          address: '#',
          text: 'Будущий макет сайта (deadline: 26.07.2022)',
          desc: 'Ссылка на сайт еще не доступна',
        },
        {
          img: require('../assets/imgs/portfolio-2.webp'),
          address: '#',
          text: 'Будущий макет сайта (deadline: 03.09.2022)',
          desc: 'Ссылка на сайт еще не доступна',
        },
        {
          img: require('../assets/imgs/portfolio-3.webp'),
          address: '#',
          text: 'Будущий макет сайта (deadline: 01.06.2022)',
          desc: 'Ссылка на сайт еще не доступна',
        },
        {
          img: require('../assets/imgs/portfolio-4.webp'),
          address: 'https://dannygolds.github.io/makeup/',
          text: 'Сайт мэйк-ап студии',
          desc: 'Ссылка на сайт "Nelli make-up"',
        },
        {
          img: require('../assets/imgs/portfolio-5.webp'),
          address: '',
          text: 'Промо сайт к фильму "Человек-паук: Нет пути домой"',
          desc: 'Cайт был удален',
        },
      ],
    }
  },
  props: {
    years: Number,
    name: String,
  },
}
</script>
<style>
.fade-enter-active {
  animation: bounceIn 2s;
}
.fade-leave-active {
  animation: bouncein 2s reverse;
}
@keyframes bounceln {
  0% {
    transform: scale(0.1);
    opacity: 0;
  }
  60% {
    transform: scale(1.2);
    opacity: 1;
  }
  100% {
    transform: scale(1);
  }
}
</style>
