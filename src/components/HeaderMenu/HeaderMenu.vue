<script>
import "./style.scss";
</script>
<template>
  <div class="headerMenu">
    <div class="headerMenu__navigationContent">
      <a href="/">
        <img src="../../assets/img/xpageLogo.svg" alt="Логотип XPage" />
      </a>
      <div class="headerMenu__navigationContent__links">
        <a class="headerMenu__navigationContent__links__link" href="">Играть</a>
        <a class="headerMenu__navigationContent__links__link" href=""
          >Смотреть</a
        >
        <a class="headerMenu__navigationContent__links__link" href=""
          >Учиться</a
        >
        <a class="headerMenu__navigationContent__links__link" href=""
          >Мероприятия</a
        >
      </div>
    </div>
    <div class="headerMenu__menuContent">
      <div class="headerMenu__menuContent__menuBurger">
        <div class="headerMenu__menuContent__menuBurger__burger">
          <span></span><span></span><span></span>
        </div>
        <p class="headerMenu__menuContent__menuBurger__title">меню</p>
      </div>
      <div class="headerMenu__menuContent__profile">
        <p class="headerMenu__menuContent__profile__userName">Геннадий П.</p>
        <img
          class="headerMenu__menuContent__profile__userAvatar"
          src="../../assets/img/profileAvatar.svg"
          alt=""
        />
      </div>
    </div>
  </div>
</template>
