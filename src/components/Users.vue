<template>
  <div class="contact">
    <div class="name">
      {{ contact.name }}<span :class="{ active: contact.active }"></span>
    </div>
    <div class="butons">
      <button @click="showHide()">Details</button
      ><button @click="activate(contact)">Active</button>
      <button class="delet" @click="delet(contact)">Delete</button>
    </div>
    <div class="name_email" v-show="showDetail">
      <div class="phone">{{ contact.phone }}</div>
      <div class="email">{{ contact.email }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["contact"],
  data() {
    return {
      showDetail: false,
    };
  },
  methods: {
    showHide() {
      this.showDetail = !this.showDetail;
    },
    activate(contact) {
      this.$emit("activate-user", contact);
    },
    delet(contact) {
      this.$emit("delete-user", contact);
    },
  },
};
</script>

<style scoped>
.contact {
  padding: 0px 10px;
  border-radius: 5px;
  margin-bottom: 15px;
  background: rgb(222, 222, 222);
}

.name {
  font-size: 28px;
  padding: 5px 0px;
  font-weight: bold;
  font-family: "Arial Rounded MT";
  border-bottom: 2px solid gray;
}

.name span {
  width: 15px;
  height: 15px;
  margin-left: 15px;
  border-radius: 50%;
  display: inline-block;
  border: 3px solid rgb(158, 158, 158);
}

.active {
  background: rgb(1, 190, 159);
}

button {
  cursor: pointer;
  border: none;
  outline: none;
  margin: 10px;
  padding: 5px 10px;
  border-radius: 5px;
  font-size: 20px;
  background: gray;
  color: whitesmoke;
  transition: all ease-in-out 0.2s;
}
button:hover,
button:active {
  background: rgb(90, 90, 90);
}

button.delet {
  background: rgb(230, 5, 110);
}

.phone {
  font-size: 24px;
  padding: 5px 0px;
  font-weight: bold;
  color: rgb(6, 121, 252);
  font-family: "Arial Rounded MT";
}
.email {
  font-size: 24px;
  padding: 5px 0px;
  font-weight: bold;
  color: blueviolet;
  font-family: "Arial Rounded MT";
}
</style>
