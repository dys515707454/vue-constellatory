<template>
  <div class="tab">
    <div
      class="tab-item"
      v-for="(item, index) in tabData" :key="index"
    >
      <tab-icon
        :iconText = "item.iconText"
        :path = "item.path"
      >
        {{ item.tabText }}
      </tab-icon>
    </div>
  </div>
</template>

<script>

import TabIcon from './Icon'

import tabData from '@/datas/tab'

import { reactive, toRefs } from 'vue'

export default {
  name: 'Tab',
  components: {
    TabIcon
  },
  setup() {
    const state = reactive({
      tabData
    })

    return {
      ...toRefs(state)
    }
  }
}
</script>

<style lang='scss'>
.tab{
  display: flex;
  flex-direction: row;
  position: fixed;
  bottom: 0;
  left: 0;
  z-index: 1;
  width: 100%;
  height: 50px;
  border-top: 1px solid #dddddd;
  background-color: #ffffff;

  .tab-item {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 20%;
    height: 100%;
  }
}
</style>