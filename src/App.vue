<template>
  <div id="app">
    <div class="main-screen">
      <div class="nav">
        <div class="nav-logo">
          <img src="@/assets/boot.svg" alt="logo">
        </div>
        <ul class="nav-menu">
          <li>
            <a class="nav-menu-link" href="#Home">Home</a>
          </li>
          <li>
            <a class="nav-menu-link" href="#Products">Products</a>
          </li>
          <li>
            <a class="nav-menu-link" href="#Basket">
              <font-awesome-icon icon="cart-plus" />
            </a>
          </li>
        </ul>
      </div>
      <div class="head-title">
        <h1 class="head-title-text">Our clothing, you comfort</h1>
        <h3 class="head-title-desc">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Obcaecati, ab.</h3>
      </div>
      <div class="arrow-scroll">
        <font-awesome-icon icon="arrow-down" />
      </div>
    </div>
    <div class="filters container">
      <div class="filters-check">
        <input class="custom-checkbox" id="men" type="checkbox">
        <label for="men">MEN</label>
        <input class="custom-checkbox" id="women" type="checkbox">
        <label for="women">WOMEN</label>
        <input class="custom-checkbox" id="child" type="checkbox">
        <label for="child">CHILDREN</label>
      </div>
      <button class="btn-primary" type="button">SEE ALL</button>
    </div>
    <div class="content container">
      <h2 class="content-title">MEN</h2>
      <div
        v-for="(item, index) in dataShoesMen"
        :key="index"
        class="content-card"
      >
        <div class="content-card-top">
          <select class="content-card-select">
            <option value="S">S</option>
            <option value="M">M</option>
            <option value="L">L</option>
          </select>
          <div class="content-card-color">
            <div class="color blue"></div>
            <div class="color yellow"></div>
            <div class="color black"></div>
          </div>
        </div>
        <div class="content-card-side">
          <div class="content-card-side-img">
            <img :src="item.img" alt="">
          </div>
        </div>
        <div class="content-card-bottom">
          <h2 class="content-card-bottom-title">{{ item.name }}</h2>
          <p class="content-card-bottom-price">{{ item.price }}</p>
        </div>
      </div>
      <h2 class="content-title">WOMEN</h2>
      <div
        v-for="(item, index) in dataShoesWomen"
        :key="index + 'women'"
        class="content-card"
      >
        <div class="content-card-top">
          <select class="content-card-select">
            <option value="S">S</option>
            <option value="M">M</option>
            <option value="L">L</option>
          </select>
          <div class="content-card-color">
            <div class="color blue"></div>
            <div class="color yellow"></div>
            <div class="color black"></div>
          </div>
        </div>
        <div class="content-card-side">
          <div class="content-card-side-img">
            <img :src="item.img" alt="">
          </div>
        </div>
        <div class="content-card-bottom">
          <h2 class="content-card-bottom-title">{{ item.name }}</h2>
          <p class="content-card-bottom-price">{{ item.price }}</p>
        </div>
      </div>
    </div>
    <div class="about-us container">
      <p class="about-us-text">Lorem ipsum dolor sit amet consectetur adipisicing elit.
        <br />Officia sunt quia officiis aspernatur, nam sapiente ex praesentium atque eligendi voluptates.
      </p>
    </div>
    <div class="contact container">
      <p>Text me</p>
      <p class="contact-email">E-mail: aka.kaizer@yandex.ru</p>
      <p class="contcat-skype">Skype - akafollen</p>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      dataShoesMen: [
        {
          name: 'Boots Army',
          price: '15,00€',
          img: require('@/assets/1.jpg')
        },
        {
          name: 'Boots',
          price: '20,00€',
          img: require('@/assets/2.jpg')
        },
        {
          name: 'Shooes',
          price: '29,00€',
          img: require('@/assets/3.jpg')
        },
        {
          name: 'Boots Pedal',
          price: '19,00€',
          img: require('@/assets/4.jpg')
        },
        {
          name: 'Army Pedal',
          price: '14,00€',
          img: require('@/assets/5.jpg')
        },
        {
          name: 'Women Pedal',
          price: '39,00€',
          img: require('@/assets/6.jpg')
        }
      ],
      dataShoesWomen: [
        {
          name: 'Women Boots',
          price: '25,00€',
          img: require('@/assets/7.jpg')
        },
        {
          name: 'Women shooes',
          price: '23,00€',
          img: require('@/assets/8.jpg')
        },
        {
          name: 'Women pedal',
          price: '45,00€',
          img: require('@/assets/9.jpg')
        }
      ]
    }
  }
}
</script>
<style lang="stylus">
@import url('https://fonts.googleapis.com/css?family=Roboto+Condensed');
#app {
  font-family 'Roboto Condensed', sans-serif
  box-sizing border-box
  height 100%
  width 100%
}
*
  margin 0
  padding 0

.container
  width 1080px
  margin 0 auto
  @media all and (min-width: 320px) and (max-width: 1079px)
    width 100%

.btn-primary
  padding 10px 35px
  font-size 24px
  background-color #e1a36c
  border none
  border-radius 6px
  color #fff

.custom-checkbox
  position absolute
  z-index -1
  opacity 0

.custom-checkbox + label
  display flex
  align-items center
  margin-right 6px

  &::before
    content ""
    display inline-block
    width 1em
    height 1em
    flex-shrink 0
    flex-grow 0
    margin-right 6px
    border 1px solid #e1a36c
    border-radius 6px
    vertical-align baseline
    background-repeat no-repeat
    background-position center center
    background-size 50% 50%

.custom-checkbox
  &:checked + label
    &::before
      border-color #e3773d
      background-color #e3773d
      background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8 8'%3e%3cpath fill='%23fff' d='M6.564.75l-3.59 3.612-1.538-1.55L0 4.26 2.974 7.25 8 2.193z'/%3e%3c/svg%3e")

.main-screen
  position relative
  height 100vh
  background-color rgba(0,0,0, 0.8)

  .nav
    display flex
    justify-content space-between
    align-items center
    position relative
    padding 12px

    &-logo
      width 50px
      height 50px

    &-menu
      display flex
      list-style none

      &-link
        margin 6px
        color #fff
        font-size 1.4rem
        text-decoration none

  .head-title
    position absolute
    top 50%
    left 50%
    transform translate(-50%, -50%)
    width 100%
    color #fff
    text-align center

    &-text
      font-size 64px

    &-desc
      margin-top 12px
      font-size 22px
      opacity 0.7

  .arrow-scroll
    position absolute
    left 50%
    top calc(100vh - 10%)
    color #fff

  &::before
    content ""
    position absolute
    left 0
    top 0
    width 100%
    height 100%
    background url("~@/assets/main-screen.jpg") no-repeat center center
    background-size cover
    opacity 0.6

.filters
  display flex
  justify-content space-between
  align-items center
  padding 32px 0

  @media all and (min-width: 320px) and (max-width: 1079px)
    width 95%
    padding 16px 0

  &-check
    display flex

    @media all and (min-width: 320px) and (max-width: 1079px)
      flex-direction column

.content
  display flex
  justify-content space-between
  flex-flow row wrap
  padding 24px 0

  @media all and (min-width: 320px) and (max-width: 1079px)
    justify-content center

  &-title
    flex-basis 100%
    position relative
    font-size 24px
    margin 42px 0
    overflow hidden

    &::after
      content "";
      position absolute
      top 50%
      margin-left 24px
      border-bottom 1px solid #000
      width 100%

  &-card
    margin 6px

    &-top
      display flex
      justify-content space-between

    &-select
      color #000

    &-color
      display flex

      .color
        width 20px
        height 20px
        margin 6px
        border-radius 50%
        border 1px solid #ccc

      .blue
        background-color #1440e7
      .yellow
        background-color #e7dc14
      .black
        background-color #0b0a01

    &-side
      &-img
        display flex
        justify-content center
        padding 24px 0
        width 333px
        img
          width 100%

        @media all and (min-width: 320px) and (max-width: 1079px)
          width 300px

    &-bottom
      display flex
      justify-content space-between
      align-items center

      &-title
        font-size 24px

      &-price
        font-size 20px

.about-us
  display flex
  justify-content center
  padding 48px 0
  text-align center
  background-color #e1be89

  &-text
    position relative
    width 600px
    padding 24px
    border 1px solid #ad8c71

    &::before
      content "ABOUT US"
      position absolute
      top 0
      left 50%
      transform translate(-50%, -50%)
      padding 8px 12px
      background #e1be89
      border-radius 6px

.contact
  padding 24px 0
  text-align center
  background-color #5f7eb4
</style>
