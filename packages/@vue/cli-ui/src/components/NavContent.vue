<template>
  <div class="nav-content">
    <NavList
      :items="items"
    >
      <template slot-scope="props">
        <slot v-bind="props"/>
      </template>
    </NavList>

    <div class="content vue-ui-disable-scroll">
      <router-view/>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    items: {
      type: Array,
      required: true
    }
  }
}
</script>

<style lang="stylus" scoped>
@import "~@/style/imports"

.nav-content
  width 100%
  height 100%
  display grid
  grid-template-columns 300px 1fr
  grid-template-rows 1fr
  grid-template-areas "nav content"
  > .nav-list
    grid-area nav
  > .content
    grid-area content
    overflow-x hidden
    overflow-y auto
</style>
