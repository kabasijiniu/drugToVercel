<template>
  <div class="table-wrapper">
    <h3>{{company +" " +update_date}}</h3>
    <el-table :data="tableData" style="width: 100%" empty-text="核对无异常">
      <el-table-column prop="name" label="药品名称" />
      <el-table-column prop="code" label="医保编码" />
      <el-table-column prop="price" label="后台价格" />
      <el-table-column prop="ybPrice" label="医保价格" />
      <el-table-column prop="hou_tai_company_name" label="后台厂家" v-if="isCompanyColumnVisible"/>
      <el-table-column prop="ybCompanyName" label="医保厂家" v-if="isCompanyColumnVisible"/>
      <el-table-column prop="wangResult" label="核对结果" />
    </el-table>
  </div>
</template>

<script setup>
import {ref, defineProps, watch, computed} from 'vue'
const props = defineProps(['data','company','update_date']);
const data = ref(props.data);
let tableData = data.value.filter(item => item.wangResult !== "信息一致");
const isCompanyColumnVisible = ref(false);




</script>

<style lang="scss" scoped>

</style>