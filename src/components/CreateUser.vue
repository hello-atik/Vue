<template>
  <div class="create_user">
    <form @submit.prevent="sendData">
      <div class="form_item">
        <span>NAME</span
        ><input type="text" placeholder="Alex Costa" v-model="name" />
      </div>
      <div class="form_item">
        <span>PHONE</span
        ><input type="text" placeholder="01950221560" v-model="phone" />
      </div>
      <div class="form_item">
        <span>EMAIL</span
        ><input type="text" placeholder="example@gmail.com" v-model="email" />
      </div>
      <div class="check">
        <span>ACTIVE</span><input type="checkbox" v-model="active" />
      </div>
      <div class="form_buttons">
        <button type="reset">Reset</button>
        <button class="create" type="submit">Create</button>
      </div>
    </form>
    <alert v-if="showAlert" @close-alert="showAlert = false"></alert>
  </div>
</template>

<script>
import Alert from "./Alert";
export default {
  components: {
    Alert,
  },
  data() {
    return {
      name: "",
      phone: "",
      email: "",
      active: false,
      showAlert: false,
    };
  },
  methods: {
    sendData() {
      let c = {
        name: this.name.trim(),
        phone: this.phone.trim(),
        email: this.email.trim(),
        active: this.active,
      };
      if (!c.name || !c.phone || !c.email) {
        this.showAlert = true;
        return;
      }
      this.$emit("add-user", c);
      this.name = "";
      this.phone = "";
      this.email = "";
      this.active = false;
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+JP&display=swap");

* {
  margin: 0px;
  padding: 0px;
}

.create_user {
  border-radius: 5px;
  padding: 15px 10px;
  background: rgb(222, 222, 222);
  margin-bottom: 15px;
  box-shadow: 0px 2px 3px 2px rgba(0, 0, 0, 0.3);
}

form {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  font-family: "Noto Sans JP", sans-serif;
}
.form_item,
.form_buttons,
.check {
  margin: 5px 15px;
}

.form_item {
  display: flex;
  align-items: center;
}

.form_item input[type="text"] {
  padding-left: 10px;
  border-radius: 3px;
  outline: none;
  border: 1px solid gray;
  min-width: 200px;
  max-width: 200px;
  height: 30px;
  line-height: 30px;
  font-size: 18px;
  font-family: "Roboto";
}

.form_item input[type="text"]::placeholder {
  font-size: 15px;
}

.form_item span,
.check span {
  margin-right: 10px;
  font-size: 17px;
}

.check {
  display: flex;
  align-items: center;
  justify-content: center;
}
.check input[type="checkbox"] {
  height: 20px;
  width: 20px;
}

.form_buttons button {
  cursor: pointer;
  border: 1px solid gray;
  border-radius: 3px;
  line-height: 30px;
  width: 70px;
  font-family: inherit;
  margin: 0px 10px;
  font-size: 18px;
  outline: none;
  transition: all ease-in-out 0.2s;
}

button:hover,
button:active {
  background: rgb(90, 90, 90);
  color: aliceblue;
}
</style>
