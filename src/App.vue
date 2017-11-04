<template>
  <div id="app">
    <ole-navbar href="/">
      <img class="logo" src="~public/hc-logo.png" alt="logo"/>
      <ole-navbar-item slot="navbar-start" href="/top">
        <router-link to="/top">Top</router-link>
      </ole-navbar-item>
      <ole-navbar-item slot="navbar-start" href="/new">
        <router-link to="/new">New</router-link>
      </ole-navbar-item>
      <ole-navbar-item slot="navbar-start" href="/show">
        <router-link to="/show">Show</router-link>
      </ole-navbar-item>
      <ole-navbar-item slot="navbar-start" href="/ask">
        <router-link to="/ask">Ask</router-link>
      </ole-navbar-item>
      <ole-navbar-item slot="navbar-start" href="/job">
        <router-link to="/job">Jobs</router-link>
      </ole-navbar-item>
      <ole-navbar-item href="https://github.com/vuejs/vue-hackernews-2.0">
        <ole-icon type="github" style="color: #333;"></ole-icon>
      </ole-navbar-item>
    </ole-navbar>
    <transition name="fade" mode="out-in">
      <router-view class="view"></router-view>
    </transition>
  </div>
</template>

<style lang="stylus">
body
  font-family -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-size 15px
  background-color lighten(#eceef1, 30%)
  margin 0
  // padding-top 55px
  color #34495e
  overflow-y scroll

.logo
  height 28px
  padding-top 10px
  padding-left  10px

a
  color #34495e
  text-decoration none

.header
  background-color #ff6600
  position fixed
  z-index 999
  height 55px
  top 0
  left 0
  right 0
  .inner
    max-width 800px
    box-sizing border-box
    margin 0px auto
    padding 15px 5px
  a
    color rgba(255, 255, 255, .8)
    line-height 24px
    transition color .15s ease
    display inline-block
    vertical-align middle
    font-weight 300
    letter-spacing .075em
    margin-right 1.8em
    &:hover
      color #fff
    &.router-link-active
      color #fff
      font-weight 400
    &:nth-child(6)
      margin-right 0
  .github
    color #fff
    font-size .9em
    margin 0
    float right



.view
  max-width 800px
  margin 0 auto
  position relative

.fade-enter-active, .fade-leave-active
  transition all .2s ease

.fade-enter, .fade-leave-active
  opacity 0

@media (max-width 860px)
  .header .inner
    padding 15px 30px

@media (max-width 600px)
  .header
    .inner
      padding 15px
    a
      margin-right 1em
    .github
      display none
</style>
