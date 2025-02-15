<script setup lang="ts">
import "./assets/styles/main.scss";
import HeaderMenu from "./components/HeaderMenu/HeaderMenu.vue";
import ArrowRightIcon from "./components/ArrowRightIcon/ArrowRightIcon.vue";
import LearnSectionFilter from "./components/LearnSectionFilter/LearnSectionFilter.vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import { ref } from "vue";
import mainBanner from "./assets/img/mainBanner.webp";
import image1 from "./assets/img/1.webp";
import image2 from "./assets/img/2.webp";
import { playSectionConfig } from "./config/constants.ts";

const images = [mainBanner, image1, image2];
const activeIndex = ref(0);
const changeSlide = (index: number) => {
  activeIndex.value = index;
};

const learnSectionFilters = [
  "Детская тренировка",
  "Для начинающих",
  "Стритбол",
  "Выезд тренера на дом",
  "12 фильтров",
];
</script>

<template>
  <header>
    <HeaderMenu />
  </header>
  <main>
    <section class="mainBanner">
      <transition name="fade" mode="out-in">
        <img
          class="mainBanner__img"
          :src="images[activeIndex]"
          alt="image"
          :key="images[activeIndex]"
        />
      </transition>
      <div class="mainBanner__content">
        <h1 class="mainBanner__content__title">
          Найди с кем поиграть в баскет
        </h1>
        <div class="mainBanner__content__interactiveContent">
          <div
            class="mainBanner__content__interactiveContent__button"
            @mouseover="changeSlide(0)"
          >
            Играй
            <img src="./assets/img/right_arrow.svg" alt="Стрелка вправо" />
          </div>
          <div
            class="mainBanner__content__interactiveContent__button"
            @mouseover="changeSlide(1)"
          >
            Учись
            <img src="./assets/img/right_arrow.svg" alt="Стрелка вправо" />
          </div>
          <div
            class="mainBanner__content__interactiveContent__button"
            @mouseover="changeSlide(2)"
          >
            Смотри
            <img src="./assets/img/right_arrow.svg" alt="Стрелка вправо" />
          </div>
        </div>
      </div>
    </section>
    <section class="playSection">
      <div class="playSection__headContent">
        <h1 class="playSection__headContent__title">Играй</h1>
        <div class="playSection__headContent__button">
          В раздел
          <ArrowRightIcon />
        </div>
      </div>
      <div class="playSection__cardPlace">
        <div
          v-for="card in playSectionConfig"
          :key="card.id"
          class="playSection__cardPlace__card"
        >
          <img
            class="playSection__cardPlace__card__img"
            :src="card.img"
            alt="Изображение карточки"
          />
          <h2 class="playSection__cardPlace__card__title">{{ card.title }}</h2>
          <p class="playSection__cardPlace__card__description">
            {{ card.description }}
          </p>
          <div class="playSection__cardPlace__card__button">
            Текст кнопки
            <ArrowRightIcon />
          </div>
        </div>
      </div>
    </section>
    <section class="learnSection">
      <div class="learnSection__headContent">
        <h1 class="learnSection__headContent__title">Учись</h1>
        <div class="learnSection__headContent__button">
          В раздел
          <ArrowRightIcon />
        </div>
      </div>
      <div class="learnSection__content">
        <div class="learnSection__content__leftSide">
          <div class="learnSection__content__leftSide__banner">
            <h1 class="learnSection__content__leftSide__banner__title">
              Мы собрали секции для детей по всему городу
            </h1>
            <LearnSectionFilter
              text="12 секций по всему городу"
              :extraClasses="[
                'learnSection__content__leftSide__banner__sectionsCount',
              ]"
            />
          </div>
          <div class="learnSection__content__leftSide__filters">
            <h1 class="learnSection__content__leftSide__filters__title">
              Подбери тренера под свой уровень
            </h1>
            <div class="learnSection__content__leftSide__filters__filtersList">
              <LearnSectionFilter
                v-for="filter in learnSectionFilters"
                :text="filter"
                :extraClasses="[
                  'learnSection__content__leftSide__filters__filter',
                ]"
              />
            </div>
          </div>
        </div>
        <div class="learnSection__content__rightSide">
          <div class="learnSection__content__rightSide__videoTutorials">
            <h1 class="learnSection__content__rightSide__videoTutorials__title">
              Видеоуроки
            </h1>
            <div
              class="learnSection__content__rightSide__videoTutorials__content"
            >
              <img
                class="learnSection__content__rightSide__videoTutorials__content__img"
                src="./assets/img/videoTutorial.png"
                alt=""
              />
              <div
                class="learnSection__content__rightSide__videoTutorials__content__textContent"
              >
                <p
                  class="learnSection__content__rightSide__videoTutorials__content__textContent__title"
                >
                  Евгений Воронов: «‎бронзовые медали - оценка труда нашей
                  команды»
                </p>
                <LearnSectionFilter
                  text="26 октября"
                  :extraClasses="[
                    'learnSection__content__rightSide__videoTutorials__content__textContent__filter',
                  ]"
                />
              </div>
            </div>
          </div>
          <div class="learnSection__content__rightSide__articles">
            <div class="learnSection__content__rightSide__articles__title">
              Статьи
              <div
                class="learnSection__content__rightSide__articles__title--arrow"
              >
                <ArrowRightIcon />
              </div>
            </div>
            <div
              class="learnSection__content__rightSide__articles__textContent"
            >
              <p
                class="learnSection__content__rightSide__articles__textContent__title"
              >
                Евгений Воронов: «‎бронзовые медали - оценка труда нашей
                команды»
              </p>
              <LearnSectionFilter
                text="26 октября"
                :extraClasses="[
                  'learnSection__content__rightSide__articles__textContent__filter',
                ]"
              />
            </div>
          </div>
          <div class="learnSection__content__rightSide__termins">
            <h1 class="learnSection__content__rightSide__termins__title">
              Термины
            </h1>
            <div class="learnSection__content__rightSide__termins__filters">
              <LearnSectionFilter
                :extraClasses="[
                  'learnSection__content__rightSide__termins__filters__filter',
                ]"
                text="Треха"
              />
              <LearnSectionFilter
                :extraClasses="[
                  'learnSection__content__rightSide__termins__filters__filter',
                ]"
                text="Трехочковый бросок"
              />
              <LearnSectionFilter
                :extraClasses="[
                  'learnSection__content__rightSide__termins__filters__filter',
                ]"
                text="36 терминов"
              />
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
  <footer>
    <section class="footerContent">
      <div class="footerContent__leftSide">
        <h1 class="footerContent__leftSide__title">
          Еще больше полезных материалов и видеоуроков<br />
          в нашем приложении
        </h1>
        <div class="footerContent__leftSide__apps">
          <div class="footerContent__leftSide__apps__item">
            <img
              class="footerContent__leftSide__apps__item__img"
              src="./assets/img/appStore.svg"
              alt="AppStore"
            />
            <div class="footerContent__leftSide__apps__item__textContent">
              <p class="footerContent__leftSide__apps__item__textContent__text">
                Download on the
              </p>
              <p class="footerContent__leftSide__apps__item__textContent__text">
                App Store
              </p>
            </div>
          </div>
          <div class="footerContent__leftSide__apps__item">
            <img
              class="footerContent__leftSide__apps__item__img"
              src="./assets/img/googlePlay.svg"
              alt="GooglePlay"
            />
            <div class="footerContent__leftSide__apps__item__textContent">
              <p class="footerContent__leftSide__apps__item__textContent__text">
                Get in on
              </p>
              <p class="footerContent__leftSide__apps__item__textContent__text">
                Google Play
              </p>
            </div>
          </div>
        </div>
        <p class="footerContent__leftSide__madeInText">Сделано в xpage</p>
      </div>
      <div class="footerContent__rightSide">
        <img
          class="footerContent__rightSide__img"
          src="./assets/img/ballForFooter.svg"
          alt="Ball image"
        />
        <div class="footerContent__rightSide__qrCode">
          <img
            class="footerContent__rightSide__qrCode__img"
            src="./assets/img/qrCode.svg"
            alt="QR-код"
          />
          <div class="footerContent__rightSide__qrCode__textContent">
            <p class="footerContent__rightSide__qrCode__textContent__phoneType">
              iOS / Android
            </p>
            <p
              class="footerContent__rightSide__qrCode__textContent__instruction"
            >
              Наведите камеру устройства на QR-<br />код, чтобы скачать
            </p>
          </div>
        </div>
      </div>
    </section>
  </footer>
</template>

<style scoped></style>
