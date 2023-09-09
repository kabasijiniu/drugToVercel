<template>
  <div>

    <TableBase :data="item.ret_except_drug_list" :company="item.company_name" v-for="(item,index) in tableData" :key="index"/>
  </div>
</template>

<script setup>
import JsonData from "../data/data.json";
import TableBase from "./TableBase.vue";
import {ref} from "vue";

const tableData = ref(JsonData);
console.log(JsonData);

</script>

<style lang="scss" scoped>

</style>