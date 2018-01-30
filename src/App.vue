<template>
  <div id="app">
    <nav-bar></nav-bar>
    <el-row :gutter="20">
      <el-col :span="16">
        <h1>Products</h1>
        <product-list></product-list>
      </el-col>
      <el-col :span="8">
        <h1>Cart</h1>
        <shopping-cart></shopping-cart>
        <p><b>Total: {{ totalCost | currency }}</b></p>
      </el-col>
    </el-row>

  </div>
</template>

<script>
import {Store} from './store/Store'

export default {
  name: 'app',
  computed: {
    totalCost(){
      return Store.totalCost
    }
  }
}
</script>
