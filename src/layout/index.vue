<template>
  <div>
    <el-container v-if="$route.name !== '404' && $route.name !== 'login'">
      <el-aside width="200px">
        <app-aside />
      </el-aside>
      <el-container>
        <el-header>
          <app-header />
        </el-header>
        <el-main
          >Main
          <router-view />
        </el-main>
      </el-container>
    </el-container>
    <router-view v-else/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import AppAside from './components/app-aside.vue'
import AppHeader from './components/app-header.vue'

export default Vue.extend({
  name: 'LayoutIndex',
  components: {
    AppAside,
    AppHeader
  }
})
</script>

<style lang="scss" scoped>
.el-container {
  min-height: 100vh;
  min-width: 960px;
}

.el-aside {
  background: #d3dce6;
}

.el-header {
  background: #b3c0d1;
}

.el-header {
  background: #fff;
  display: flex;
  align-items: center;
}

.el-main {
  background: #e9eef3;
}
</style>