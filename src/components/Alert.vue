<template>
  <div class="drop">
    <div class="alert">
      <h2>Alert !!!</h2>
      <p>Name , Phone & Email can not be blank.</p>
      <div class="close" @click="closeAlert">Close</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    closeAlert() {
      this.$emit("close-alert");
    },
  },
};
</script>

<style scoped>
.drop {
  margin: 0px;
  padding: 0px;
  display: flex;
  position: absolute;
  align-items: center;
  justify-content: center;

  top: 0px;
  left: 0px;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.8);
}

.alert {
  width: 400px;
  height: 200px;
  border-radius: 5px;
  background: #dfdfdf;
}
h2 {
  font-size: 28px;
  color: tomato;
  font-weight: bolder;
  padding-bottom: 10px;
  border-bottom: 3px solid gray;
  font-family: "Arial Rounded MT";
}

p {
  font-size: 18px;
  font-family: "Arial Rounded MT";
}

.close {
  cursor: pointer;
  margin-top: 15px;
  border-radius: 5px;
  padding: 10px 15px;
  background: teal;
  color: floralwhite;
  display: inline-block;
}
</style>
