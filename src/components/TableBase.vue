<template>
  <div class="table-wrapper">
    <h2>{{company}}</h2>
    <el-table :data="tableData" style="width: 100%" empty-text="核对无异常">
      <el-table-column prop="name" label="药品名称" />
      <el-table-column prop="code" label="医保编码" />
      <el-table-column prop="price" label="后台价格" />
      <el-table-column prop="yb_price" label="医保价格" />
      <el-table-column prop="hou_tai_company_name" label="后台厂家" v-if="isCompanyColumnVisible"/>
      <el-table-column prop="yb_company_name" label="医保厂家" v-if="isCompanyColumnVisible"/>
      <el-table-column prop="result" label="核对结果" />
    </el-table>
  </div>
</template>

<script setup>
import {ref, defineProps, watch} from 'vue'
const props = defineProps(['data','company']);
const tableData = ref(props.data);
const isCompanyColumnVisible = ref(false);

watch(() => tableData, (newVal, oldVal) => {
  if(tableData.hou_tai_company_name !== "" && tableData.yb_company_name !==""){
    isCompanyColumnVisible.value = true;
  }
})


</script>

<style lang="scss" scoped>

</style>