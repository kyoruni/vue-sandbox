<template>
  <div id="app">
    <Header/>
    <div class="container-fluid">
      <div class="row">
        <div class="col-sm-2 p-0">
          <left/>
        </div>
        <div class="col-sm-10 p-0">
          <right/>
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
  }
}
</script>

<style scoped>
#app {
  background: pink;
}
.container-fluid{
  overflow: hidden;
}
</style>
