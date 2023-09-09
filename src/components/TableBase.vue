<template>
  <div class="table-wrapper">
    <h1>{{company}}</h1>
    <el-table :data="tableData" style="width: 100%">

      <el-table-column prop="name" label="药品名称" />
      <el-table-column prop="code" label="医保编码" />
      <el-table-column prop="price" label="后台价格" />
      <el-table-column prop="yb_price" label="医保价格" />
      <el-table-column prop="hou_tai_company_name" label="后台厂家" />
      <el-table-column prop="yb_company_name" label="医保厂家" />
      <el-table-column prop="result" label="核对结果" />
    </el-table>
  </div>
</template>

<script setup>
import { ref ,defineProps} from 'vue'
const props = defineProps(['data','company']);
const tableData = ref(props.data);
const company = ref(props.company);
</script>

<style lang="scss" scoped>

</style>