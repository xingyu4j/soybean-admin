<template>
  <div class="h-full">
    <fs-crud ref="crudRef" v-bind="crudBinding"></fs-crud>
  </div>
</template>

<script lang="ts" setup>
import { onMounted } from 'vue';
import { useFs } from '@fast-crud/fast-crud';
import createCrudOptions from './crud';
const { crudRef, crudBinding, crudExpose } = useFs({ createCrudOptions });
// 页面打开后获取列表数据
onMounted(() => {
  crudExpose.doRefresh();
});
</script>
