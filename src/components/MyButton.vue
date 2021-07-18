<template>
  <div class="container">
    <button 
      :class="[
        'my-button',
        `my-button-${type}`,
        size,
        { 
          'round': round,
          'disabled': disabled,
        },

      ]"
      @click="click"
    >
      <slot>默认按钮</slot>
    </button>
  </div>
</template>

<script>
export default {
  name: "MyButton",
  props: {
    type: {
      type: String,
      default: "default",
      validator: (value) => {
        return ["primary", "success", "info", "warning", "danger", "default"].includes(value);
      }
    },
    size: {
      type: String,
      default: "default",
      validator: (value) => {
        return ["small", "mini", "default"].includes(value);
      }
    },
    round: {
      type: Boolean,
      default: false
    },
    disabled: {
      type: Boolean,
      default: false
    },
  },
  data(){
    return {}
  },
  methods: {
    click(e){
      this.$emit('click',e);
    }
  }
}
</script>
<style scoped lang="scss">
.my-button {
  display: inline-block;
  box-sizing: border-box;
  padding: 12px 20px;
  text-align: center;
  cursor: pointer;
  font-size: 14px;
  color: #606266;
  background: #fff;
  border: 1px solid #dcdfe6;
  border-radius: 4px;
  &:hover {
    color: #606266;
    border-color: #c6e2ff;
    background-color: #dcdfe6;
  }
  &.disabled {
    cursor: not-allowed;
  }
  &.disabled:hover {
    color: #606266;
    border-color: #dcdfe6;
    background-color: #fff;
  }
}
.my-button-primary {
  background-color: #409eff;
  border-color: #409eff;
  color: #fff;
  &:hover {
    background: #66b1ff;
    border-color: #66b1ff;
    color: #fff;
  }
  &.disabled {
    cursor: not-allowed;
  }
  &.disabled:hover {
    color: #fff;
    border-color: #409eff;
    background-color: #409eff;
  }
}
.my-button-success {
  background-color: #67c23a;
  border-color: #67c23a;
  color: #fff;
  &:hover {
    background: #85ce61;
    border-color: #85ce61;
    color: #fff;
  }
  &.disabled {
    cursor: not-allowed;
  }
  &.disabled:hover {
    color: #fff;
    border-color: #67c23a;
    background-color: #67c23a;
  }
}
.my-button-info {
  background-color: #909399;
  border-color: #909399;
  color: #fff;
  &:hover {
    background: #a6a9ad;
    border-color: #a6a9ad;
    color: #fff;
  }
  &.disabled {
    cursor: not-allowed;
  }
  &.disabled:hover {
    color: #fff;
    border-color: #909399;
    background-color: #909399;
  }
}
.my-button-warning {
  background-color: #e6a23c;
  border-color: #e6a23c;
  color: #fff;
  &:hover {
    background: #ebb563;
    border-color: #ebb563;
    color: #fff;
  }
  &.disabled {
    cursor: not-allowed;
  }
  &.disabled:hover {
    color: #fff;
    border-color: #e6a23c;
    background-color: #e6a23c;
  }
}
.my-button-danger {
  background-color: #f56c6c;
  border-color: #f56c6c;
  color: #fff;
  &:hover {
    background: #f78989;
    border-color: #f78989;
    color: #fff;
  }
  &.disabled {
    cursor: not-allowed;
  }
  &.disabled:hover {
    color: #fff;
    border-color: #f56c6c;
    background-color: #f56c6c;
  }
}
.small {
  padding: 9px 15px;
  font-size: 12px;
  border-radius: 3px;
}
.mini {
  padding: 7px 15px;
  font-size: 12px;
  border-radius: 3px;
}
.round {
  border-radius: 30px;
}

</style>