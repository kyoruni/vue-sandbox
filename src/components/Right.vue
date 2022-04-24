<template>
  <div class="right">
    <click-event v-if="showClickEvent"/>
  </div>
</template>

<script>
import ClickEvent from '@/components/pages/ClickEvent/ClickEvent'

export default {
  props: [
    'currentMenu',
  ],
  components: {
    ClickEvent,
  },
  computed: {
    showClickEvent () {
      return this.currentMenu === 'ClickEvent'
    }
  },
}
</script>
