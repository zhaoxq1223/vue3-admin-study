<template>
  <el-dropdown
    v-bind="$attrs"
    trigger="click"
    class="theme"
    @command="handleSetTheme"
  >
    <!-- 图标 -->
    <div id="guide-theme">
      <el-tooltip :content="$t('msg.navBar.themeChange')">
        <SvgIcon icon="change-theme" />
      </el-tooltip>
    </div>
    <!-- menu -->
    <template #dropdown>
      <el-dropdown-menu>
        <el-dropdown-item command="color">
          {{ $t('msg.theme.themeColorChange') }}
        </el-dropdown-item>
      </el-dropdown-menu>
    </template>
  </el-dropdown>
  <!-- 弹出层 -->
  <div>
    <SelectColor v-model="selectColorVisible" />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import SelectColor from './components/SelectColor.vue'

const handleSetTheme = (command) => {
  selectColorVisible.value = true
}

const selectColorVisible = ref(false)
</script>

<style lang="scss" scoped>
</style>
