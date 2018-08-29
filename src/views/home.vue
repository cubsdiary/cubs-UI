<template>
  <div class="home">
    Home
    <button type="button" name="button" @click="showNotify">click me !</button>
    <Notification content="test notify"/>
  </div>
</template>

<script>
export default {
  methods: {
    showNotify () {
      this.$notify({
        content: 'test $notify',
        btn: 'close'
      })
    }
  }
}
</script>

<style scoped lang="stylus">
</style>
