<template>
  <div class="node-tree">
    <span>{{ node.employeeName }}</span>

    <ul class="tree-item" v-if="node.children && node.children.length">
      <EmployeeItem
        v-for="child in node.children"
        :node="child"
        :key="child.id"
      ></EmployeeItem>
    </ul>
  </div>
</template>

<script>
export default {
  name: "EmployeeItem",
  props: {
    node: Object
  }
};
</script>
<style>
.node-tree {
  color: darkslategrey;
}
.tree-item {
  padding-left: 80px;
  margin: 0;
}
</style>
