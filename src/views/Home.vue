<template>
  <div class="home">
    <MyButton>默认按钮</MyButton>
    <MyButton type="info">默认按钮</MyButton>
    <MyButton type="primary">默认按钮</MyButton>
    <MyButton type="danger">默认按钮</MyButton>
    <MyButton type="warning">默认按钮</MyButton>
    <MyButton type="success">默认按钮</MyButton>
    <br>
    <MyButton type="danger" size="small">默认按钮</MyButton>
    <MyButton type="danger" size="mini">默认按钮</MyButton>
    <br>
    <MyButton round size="mini" :disabled="true">禁用</MyButton>
    <MyButton round size="mini" type="info" :disabled="true">禁用</MyButton>
    <MyButton round size="mini" type="danger" :disabled="true">禁用</MyButton>
    <MyButton round size="mini" type="warning" :disabled="true">禁用</MyButton>
    <MyButton round size="mini" type="success" :disabled="true">禁用</MyButton>
  </div>
</template>

<script>
import MyButton from "@/components/MyButton";
export default {
  name: "Home",
  components: {
    MyButton,
  },
};
</script>
