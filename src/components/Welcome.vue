<template>
  <div>
    <h3>Welcome</h3>
    <div class="moreRules">
      <div class="moreRulesIn" v-for="(item, index) in addForm.moreNotifyObject" :key="item.key">
        <el-form-item
          label="field"
          :prop="'moreNotifyObject.' + index +'.field'"
          :rules="[{required: true, message: '请完善信息'}]"
        >
          <el-input v-model="item.field" placeholder="请输入field" class="el-select_box"></el-input>
        </el-form-item>
        <el-form-item
          label="name"
          :prop="'moreNotifyObject.'+ index +'.name'"
          :rules="[{required: true, message: '请完善信息'}]"
        >
          <el-input v-model="item.name" placeholder="请输入name" class="el-select_box"></el-input>
        </el-form-item>
        <el-form-item
          label="max"
          :prop="'moreNotifyObject.'+ index +'.max'"
          :rules="[{required: true, message: '请完善信息'}]"
        >
          <el-input v-model="item.max" placeholder="请输入max" class="el-select_box"></el-input>
        </el-form-item>
        <el-button @click="deleteRules(item, index)">删除</el-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      addForm: {
        moreNotifyObject: [
          {
            field: "",
            name: "",
            max: ""
          },
          {
            field: "",
            name: "",
            max: ""
          }
        ]
      }
    };
  },
  created() {
    this.initData();
  },
  methods: {
    initData() {
      this.addForm.moreNotifyObject = [];
    },
    addUser() {
      this.addForm.moreNotifyObject.push({
        field: "",
        name: "",
        max: ""
      });
    },
    deleteRules(item, index) {
      this.index = this.addForm.moreNotifyObject.indexOf(item);
      if (index !== -1) {
        this.addForm.moreNotifyObject.splice(index, 1);
      }
    }
  }
};
</script>

<style scoped>
</style>
