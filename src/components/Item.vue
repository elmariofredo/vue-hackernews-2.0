<template>
    <ole-column>
      <ole-box>
        <div slot="left">{{ item.score }}</div>
        <div class="news-item">
          <span class="title">
            <template v-if="item.url">
              <a :href="item.url" target="_blank" rel="noopener">{{ item.title }}</a>
              <span class="host"> ({{ item.url | host }})</span>
            </template>
            <template v-else>
              <router-link :to="'/item/' + item.id">{{ item.title }}</router-link>
            </template>
          </span>
        </div>
        <span class="meta">
          <span v-if="item.type !== 'job'" class="by">
            by <router-link :to="'/user/' + item.by">{{ item.by }}</router-link>
          </span>
          <span class="time">
            {{ item.time | timeAgo }} ago
          </span>
          <span v-if="item.type !== 'job'" class="comments-link">
            | <router-link :to="'/item/' + item.id">{{ item.descendants }} comments</router-link>
          </span>
          <span class="label" v-if="item.type !== 'story'">{{ item.type }}</span>
        </span>
      </ole-box>
    </ole-column>
</template>

<script>
import { timeAgo } from '../util/filters'

export default {
  name: 'news-item',
  props: ['item'],
  // http://ssr.vuejs.org/en/caching.html#component-level-caching
  serverCacheKey: ({ item: { id, __lastUpdated, time }}) => {
    return `${id}::${__lastUpdated}::${timeAgo(time)}`
  }
}
</script>

<style lang="stylus">
  .news-item
    background-color #fff
    // padding 20px 30px 20px 80px
    border-bottom 1px solid #eee
    position relative
    line-height 20px
  .score
    color #ff6600
    font-size 1.1em
    font-weight 700
    width 40px
    height 40px
    text-align center
  .meta, .host
    font-size .85em
    color #828282
    a
      color #828282
      text-decoration underline
      &:hover
        color #ff6600
</style>
