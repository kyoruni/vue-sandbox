<template>
  <div class="click-event p-2">
    <h2>click event</h2>
    <h3>残りHP：{{ hp }}</h3>
    <b-alert show variant="info" v-if="showAlertInfo">{{ message }}</b-alert>
    <b-alert show variant="danger" v-if="showAlertDanger">{{ message }}</b-alert>
    <b-alert show variant="success" v-if="showAlertSuccess">{{ message }}</b-alert>
    <b-button variant="danger" @click="clickDamage()" :disabled="isDisabledDamageButton">ダメージ</b-button>
    <b-button variant="primary" @click="clickRecovery()" :disabled="isDisabledRecoveryButton">かいふく</b-button>
    <b-button variant="secondary" @click="clickReset()">リセット</b-button>
  </div>
</template>

<script>

export default {
  data () {
    return {
      hp: 0,
      message: '',
      alertType: '',
    }
  },
  computed: {
    showAlertInfo () {
      return this.alertType === 'info'
    },
    showAlertDanger () {
      return this.alertType === 'danger'
    },
    showAlertSuccess () {
      return this.alertType === 'success'
    },
    maxHp () {
      return 10
    },
    minHp () {
      return 0
    },
    isDisabledDamageButton () {
      return this.hp === this.minHp
    },
    isDisabledRecoveryButton () {
      return this.hp === this.maxHp
    },
  },
  methods: {
    initComponent () {
      this.hp = 10
      this.setAlert('info', 'ボタンを押してね')
    },
    clickDamage () {
      if (this.minHp < this.hp) {
        this.hp--
        this.setAlert('danger', '1のダメージを与えた！')
      } else {
        this.setAlert('danger', 'もうダメージを与えられません！')
      }
    },
    clickRecovery () {
      if (this.hp < this.maxHp) {
        this.hp++
        this.setAlert('success', '1 HPが回復した！')
      } else {
        this.setAlert('danger', `最大HP（${this.maxHp}）を超えて回復はできません！`)
      }
    },
    clickReset () {
      this.initComponent()
    },
    setAlert (type, message) {
      this.alertType = type
      this.message = message
    },
  },
  created () {
    this.initComponent()
  }
}
</script>
