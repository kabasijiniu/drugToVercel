<template>
  <div>

    <TableBase :data="item.ret_except_drug_list" :company="item.company_name"  :update_date="item.start_date" v-for="(item,index) in tableData" :key="index"/>
  </div>
</template>

<script setup>
import JsonData from "../data/data.json";
import TableBase from "./TableBase.vue";
import {computed, ref, watch} from "vue";

const tableData = ref(JsonData);







const isVisible = ref(true);


</script>

<style lang="scss" scoped>

</style>