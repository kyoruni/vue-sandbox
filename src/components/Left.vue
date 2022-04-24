<template>
  <div class="left">
    <b-list-group>
      <b-list-group-item
        button
        v-for="menuItem in menuItems"
        :key="menuItem.title"
        @click="menuClick(menuItem.componentName)">
        {{ menuItem.title }}
      </b-list-group-item>
      <b-list-group-item href="#some-link">Awesome link</b-list-group-item>
      <b-list-group-item href="#" active>Link with active state</b-list-group-item>
      <b-list-group-item href="#">Action links are easy</b-list-group-item>
      <b-list-group-item href="#foobar" disabled>Disabled link</b-list-group-item>
    </b-list-group>
  </div>
</template>

<script>
import menuItems from '@/assets/menu-items.json'

export default {
  data () {
    return {
      menuItems,
    }
  },
  methods: {
    menuClick (componentName) {
      this.$emit('changeMenu', componentName)
    }
  },
}
</script>

<style scoped>
.left {
  background: aqua;
}
</style>
