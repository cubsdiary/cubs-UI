<template>
  <transition name="fade" @after-leave="afterLeave" @after-enter="afterEnter">
    <div
      class="notification"
      :style="style"
      v-show="visible"
      @mouseenter="clearTimer"
      @mouseleave="createTimer"
      >
      <span class="content">{{content}}</span>
      <a href="#" class="btn" @click.prevent="handleClose">{{btn || '关闭'}}</a>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'Notification',
  props: {
    content: {
      type: String,
      required: true
    },
    btn: {
      type: String,
      default: '关闭'
    }
  },
  data () {
    return {
      visible: true
    }
  },
  computed: {
    style () {
      return {}
    }
  },
  methods: {
    handleClose () {
      this.$emit('close')
    },
    afterLeave () {
      this.$emit('closed')
    },
    afterEnter () {
    },
    clearTimer () {
    },
    createTimer () {
    }
  }
}
</script>

<style scoped lang="stylus">
  .fade-enter-active, .fade-leave-active
    transition: opacity .5s
  .fade-enter, .fade-leave-to
    opacity: 0
  .notification
    display: flex;background-color: #303030
    color: rgba(255, 255, 255, 1)
    align-items: center
    padding: 20px
    position: fixed
    min-width: 280px
    box-shadow: 0 0 10px 3px #0CC
    flex-wrap: wrap
    transition: all .3s
  .content
    padding: 0
  .btn
    color: #ff4081
    padding-left: 24px
    margin-left: auto
    cursor: pointer
</style>
