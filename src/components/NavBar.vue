<template>
	<el-menu theme="dark" :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
	  <el-menu-item index="1">ThreeSixtyNine Store</el-menu-item>
	  <el-submenu index="2">
	    <template slot="title">More Items</template>
	    <el-menu-item index="2-1">Papyrus</el-menu-item>
	    <el-menu-item index="2-2">CupHead</el-menu-item>
	    <el-menu-item index="2-3">Mugman</el-menu-item>
	  </el-submenu>
	  <el-menu-item index="3">
      <a href="#" target="_blank">Even More</a>
    </el-menu-item>
	</el-menu>
</template>

<script>
export default {
    data() {
      return {
        activeIndex: '1',
        activeIndex2: '1'
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>
