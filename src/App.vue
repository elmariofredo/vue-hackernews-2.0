<template>
  <div id="app">
    <ole-navbar href="/">
      <img class="logo" src="~public/logo-48.png" alt="logo" width="112"
        height="28"/>
      <ole-navbar-item slot="navbar-start" href="/top">
        Top
      </ole-navbar-item>
      <ole-navbar-item slot="navbar-start" href="/new">
        New
      </ole-navbar-item>
      <ole-navbar-item slot="navbar-start" href="/show">
        Show
      </ole-navbar-item>
      <ole-navbar-item slot="navbar-start" href="/ask">
        Ask
      </ole-navbar-item>
      <ole-navbar-item slot="navbar-start" href="/job">
        Jobs
      </ole-navbar-item>
      <ole-navbar-item href="https://github.com/vuejs/vue-hackernews-2.0">
        <ole-icon type="github" style="color: #333;"></ole-icon>
      </ole-navbar-item>

    </ole-navbar>
    <ole-section>
      <router-view class="view"></router-view>
    </ole-section>
  </div>
</template>

<style lang="stylus">
body
  font-family -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-size 15px
  background-color lighten(#eceef1, 30%)
  margin 0
  padding-top 55px
  color #34495e
  overflow-y scroll

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

.logo
  width 24px
  margin-right 10px
  display inline-block
  vertical-align middle

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
