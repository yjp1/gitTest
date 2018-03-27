<template>
  <div class="components-container">
    <div class="info">百度富文本编辑器UEditor融入vue-cli</div>
    <div class="editor-container">
      <UE :defaultMsg=defaultMsg :config=config ref="ue"></UE>

      <button @click="getUEContent()">获取内容</button>
    </div>
  </div>
</template>
<style>
  .info{
    border-radius: 10px;
    line-height: 20px;
    padding: 10px;
    margin: 10px;
    background-color: #ffffff;
  }
</style>
<script>
import UE from '../components/ue/ue.vue'

export default {
  components: {UE},
  data () {
    return {
      defaultMsg: '这里是UE测试',
      config: {
        initialFrameWidth: null,
        initialFrameHeight: 200
      }
    }
  },
  methods: {
    getUEContent () {
      let content = this.$refs.ue.getUEContent()
      this.$notify({
        title: '获取成功，可在控制台查看！',
        message: content,
        type: 'success'
      })
      console.log(content)
    }
  }
}
</script>
