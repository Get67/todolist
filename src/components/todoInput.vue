<template>
  <div class="input-group mb-3">
    <div class="input-group-prepend">
      <span class="input-group-text" id="basic-addon1">新建任务</span>
    </div>
    <input
      type="text"
      class="form-control"
      placeholder="请输入任务名称"
      aria-label="Username"
      aria-describedby="basic-addon1"
      v-model="taskname"
    />
    <button class="btn-primary" @click="onsubmit">提交</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      taskname: "",
    };
  },
  emits: ["addtask"],
  methods: {
    onsubmit() {
      this.$emit("addtask", this.taskname);
      this.taskname = "";
    },
  },
};
</script>

<style scoped>
.input-group {
  width: 500px;
  margin: 0 auto;
}
</style>