<template>
  <div class="home">
    Home
    <button type="button" name="button" @click="showNotify">click me !</button>
    <!-- <Notification content="test notify"/> -->
    <tabs :value="tabValue" @change="handleChangeTab">
      <tab label="tab1" index="1">
        <span>tab content 1</span>
      </tab>
      <tab index="2">
        <span slot="label" style="color:red;">tab2</span>
        <span>tab content 2</span>
      </tab>
      <tab label="tab3" index="3">
        <span>tab content 3</span>
      </tab>
    </tabs>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tabValue: '1'
    }
  },
  mounted () {
  },
  methods: {
    showNotify () {
      this.$notify({
        content: 'test $notify',
        btn: 'close'
      })
    },
    handleChangeTab (index) {
      this.tabValue = index
    }
  }
}
</script>

<style scoped lang="stylus">
</style>
