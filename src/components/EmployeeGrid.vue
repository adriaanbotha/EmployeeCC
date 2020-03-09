<template>
  <EmployeeItem class="grid" :node="processEmployeeData[0]" />
</template>

<script>
import EmployeeItem from "@/components/EmployeeItem";

export default {
  name: "EmployeeGrid",
  props: ["inputData"],
  components: {
    EmployeeItem
  },
  computed: {
    processEmployeeData: function() {
      // Create root for top-level node(s)
      const root = [];
      const base = [...this.inputData];

      base.forEach(node => {
        // No parentId means top level
        if (!node.managerId) {
          return root.push(node);
        }
        // Insert node as child of parent in base array
        const parentIndex = base.findIndex(el => el.id === node.managerId);
        if (!base[parentIndex].children) {
          return (base[parentIndex].children = [node]);
        }
        base[parentIndex].children.push(node);
      });

      return root;
    }
  }
};
</script>
<style>
.grid {
  border: #2c3e50 1px;
  border-style: solid;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
}
</style>
