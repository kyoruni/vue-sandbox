<template>
  <div id="app">
    <Header/>
    <div class="container-fluid">
      <div class="row">
        <div class="col-sm-2 p-0">
          <left @changeMenu="changeMenu($event)"/>
        </div>
        <div class="col-sm-10 p-0">
          <right :currentMenu="currentMenu"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from '@/components/Header'
import Left from '@/components/Left'
import Right from '@/components/Right'

export default {
  name: "App",
  components: {
    Header,
    Left,
    Right,
  },
  data () {
    return {
      currentMenu: 'xxx',
    }
  },
  methods: {
    changeMenu (componentName) {
      console.log('changeMenu')
      console.log(componentName)
      this.currentMenu = componentName
      console.log(this.currentMenu)
    }
  }
}
</script>
