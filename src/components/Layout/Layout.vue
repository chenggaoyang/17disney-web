<template>
  <div class="layout">
    <layout-header></layout-header>
    <div class="ds-first">
      <div class="ds-first__cover"></div>
      <div class="container">
        <div class="ds-first__icon icon--pep icon__shanghai-disney-resort"></div>
        <h1 class="ds-first__title">上海迪士尼乐园</h1>
        <ds-tab-home :routes="homeTab"></ds-tab-home>
      </div>
      <ds-map></ds-map>
    </div>

    <div class="layout-main">
      <transition name="fade" mode="out-in">
        <router-view></router-view>
      </transition>
    </div>
    <layout-footer></layout-footer>
  </div>
</template>

<script>
import LayoutHeader from '@/components/Layout/LayoutHeader'
import LayoutFooter from '@/components/Layout/LayoutFooter'
import DsMap from '@/components/DsMap/DsMap.vue'
import DsTabHome from '@/components/DsTab/DsTabHome'
export default {
  name: 'layout',
  components: {
    LayoutHeader, LayoutFooter, DsMap, DsTabHome
  },
  data() {
    return {
      homeTab: [
        {
          'name': '客流预测',
          'icon': 'business-excellence',
          'to': '/forecast'
        },
        {
          'name': '历史等候',
          'icon': 'magic-morning',
          'to': '/history'
        }
      ]
    }
  },
  computed: {

  }
}
</script>

<style lang="stylus">
.layout {
  &-main {
    overflow: hidden;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
  }

  &-content {
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    position: relative;
    height: 100%;
    overflow: auto;
  }

  &-footer {
  }
}
</style>
