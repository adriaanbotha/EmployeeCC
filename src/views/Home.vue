<template>
  <div class="home">
    <div class="title">Results for Employee data shown below</div>
    <EmployeeGrid :inputData="this.employeeData" />
  </div>
</template>

<script>
import EmployeeGrid from "@/components/EmployeeGrid";

export default {
  name: "Home",
  components: {
    EmployeeGrid
  },
  data: function() {
    return {
      employeeData: [
        { employeeName: "Alan", id: "100", managerId: "150" },
        { employeeName: "Martin", id: "220", managerId: "100" },
        { employeeName: "Jamie", id: "150", managerId: "" },
        { employeeName: "Alex", id: "275", managerId: "100" },
        { employeeName: "Steve", id: "400", managerId: "150" },
        { employeeName: "David", id: "190", managerId: "400" }
      ]
    };
  }
};
</script>
<style>
.title {
  padding: 20px 0 60px 0;
  font-weight: bold;
}
</style>
