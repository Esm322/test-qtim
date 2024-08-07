<template>
  <header class="header">
    <div class="container header__container">
      <NuxtLink :to="{ name: 'Main' }" href="#" class="header__logo-link">
        <img src="/assets/img/Qtim.svg" alt="QTIM" class="header__logo">
      </NuxtLink>

      <nav class="header__nav nav">
        <ul class="nav__list list-reset">
          <li class="nav__item">
            <a href="#" class="nav__link">
              Works
            </a>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">
              About
            </a>
          </li>
        </ul>
      </nav>

      <button class="header__btn-lang btn-reset">
        <img src="/assets/img/united kingdom.svg" alt="lang" class="header__btn-lang-img">
      </button>

      <button class="header__btn-starts btn-reset">
        Let’s work
      </button>
    </div>
  </header>

  <NuxtPage />

  <footer class="footer">
    <div class="container footer__container">
      <h2 class="footer__title">
        Is there a project?
      </h2>

      <div class="footer__wrapper-middle">
        <p class="footer__text">
          Let’s work together
        </p>
        <ul class="footer__list list-reset">
          <li class="footer__item">
            <p class="footer__item-info">
              For all questions
            </p>
            <p class="footer__item-info">
              +7 (920) 278—00—68
            </p>
            <p class="footer__item-info">
              qtim@agency.com
            </p>
          </li>
          <li class="footer__item">
            <p class="footer__item-info">
              Office in Russia
            </p>
            <p class="footer__item-info">
              139 Ruben Station Lake Drew, NM 52678
            </p>
            <button class="footer__item-btn btn-reset">
              <img src="/assets/img/Frame301.svg" alt="tg">
            </button>
          </li>
          <li class="footer__item">
            <p class="footer__item-info">
              Office in Dubai
            </p>
            <p class="footer__item-info">
              139 Ruben Station Lake Drew, NM 52678
            </p>
            <button class="footer__item-btn btn-reset">
              <img src="/assets/img/Frame301.svg" alt="tg">
            </button>
          </li>
        </ul>
      </div>

      <nav class="footer__nav nav">
        <ul class="nav__list list-reset">
          <li class="nav__item">
            <a href="#" class="nav__link">
              Facebook
            </a>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">
              Instagram
            </a>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">
              Telegram
            </a>
          </li>
          <li class="nav__item">
            <button class="nav__btn btn-reset">
              Go
            </button>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">
              Behance
            </a>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">
              Linkedn
            </a>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">
              Privacy Policy
            </a>
          </li>
        </ul>
      </nav>
    </div>
  </footer>
</template>
