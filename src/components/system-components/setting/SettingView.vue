<template>
  <q-tab-panels
      v-model="model"
      animated
      swipeable
      vertical
      transition-prev="jump-up"
      transition-next="jump-up"
  >
    <q-tab-panel v-for="item in list" :name="item.entity.id">
      <component :is="item.entity.value" :set="item.entity"></component>
    </q-tab-panel>
  </q-tab-panels>
</template>
<script setup lang="ts">
import {AppSetting, Tree} from "@/components/system-components/model/system";

const model = defineModel('tab', {default: ''})
const props = defineProps<{
  list: Tree<AppSetting>[]
}>()
</script>


<style scoped>

</style>