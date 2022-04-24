<template>
  <div id="app" class="container-fluid">
    <div class="row">
      <div class="col-sm-2 p-0">
        <left/>
      </div>
      <div class="col-sm-10 p-0">
        <right/>
      </div>
    </div>
  </div>
</template>

<script>
import Left from '@/components/Left'
import Right from '@/components/Right'

export default {
  name: "App",
  components: {
    Left,
    Right
  }
}
</script>

<style scoped>
#app {
  background: pink;
}
</style>
