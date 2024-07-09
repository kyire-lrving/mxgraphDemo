<template>
  <div id="app">
    <el-tabs v-model="selectRoute" @tab-click="handleClick" type="border-card">
      <el-tab-pane v-for="item in tabArr" :key="item.route" :label="item.name" :name="item.name"> </el-tab-pane>
      <compontent :is="selectRoute"></compontent>
    </el-tabs>
  </div>
</template>

<script>
import demoFrist from '@/components/demoFrist'
import demoConfig from '@/components/demoConfig'
import mxHierarchicalLayout from '@/components/mxHierarchicalLayout'
export default {
  name: 'App',
  components: {
    demoFrist,
    demoConfig,
    mxHierarchicalLayout
  },
  data() {
    return {
      selectRoute: 'demo-frist',
      tabArr: [
        {
          name: '第一次小demo',
          route: 'demo-frist'
        },
        {
          name: 'mxgraph的自定义配置',
          route: 'demo-config'
        },
        {
          name: '绘制具备树形结构的拓扑图',
          route: 'mxHierarchicalLayout'
        }
      ]
    }
  },
  methods: {
    handleClick(tab) {
      this.selectRoute = this.tabArr[tab.index].route
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
@import './style/index.scss';
</style>
