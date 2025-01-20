<template>
  <VirtualWaterfall
    :virtual="waterfallOption.virtual"
    :gap="waterfallOption.gap"
    :preload-screen-count="waterfallOption.preloadScreenCount"
    :item-min-width="waterfallOption.itemMinWidth"
    :max-column-count="waterfallOption.maxColumnCount"
    :min-column-count="waterfallOption.minColumnCount"
    :calc-item-height="calcItemHeight"
    :items="result.list"
  >
    <template #default="scope">
      <Card
        v-if="scope?.item"
        :item="scope.item"
        :only-image="waterfallOption.onlyImage"
      >
      </Card>
    </template>
  </VirtualWaterfall>
</template>

<script lang="ts" setup>
const { waterfallOption, result, calcItemHeight } = useWaterfall();
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  background: #f1f2f6;
  user-select: none;
}
#__nuxt {
  height: 100%;
}
</style>
