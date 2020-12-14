<template>
  <div>
    <heading />
    <create-user @add-user="addUser($event)" />
    <users
      v-for="contact in contacts"
      :key="contact.phone"
      :contact="contact"
      @activate-user="activateUser(contact)"
      @delete-user="deleteUser(contact)"
    />
  </div>
</template>

<script>
import Heading from "../components/Heading.vue";
import CreateUser from "../components/CreateUser.vue";
import Users from "../components/Users.vue";

export default {
  name: "Contacts",
  components: {
    Heading,
    CreateUser,
    Users,
  },
  data() {
    return {
      contacts: [
        {
          name: "Kamal Hassan",
          phone: "01845231345",
          email: "kamalhassan@gmail.com",
          active: true,
        },
        {
          name: "Ashik Elahi",
          phone: "01773457411",
          email: "ashikelahi@gmail.com",
          active: false,
        },
        {
          name: "Monirul Islam",
          phone: "01933672165",
          email: "monirulislam@gmail.com",
          active: true,
        },
      ],
    };
  },
  methods: {
    activateUser(contact) {
      contact.active = !contact.active;
    },
    deleteUser(contact) {
      this.contacts = this.contacts.filter((c) => c.phone !== contact.phone);
    },
    addUser(contact) {
      this.contacts.push(contact);
    },
  },
};
</script>

<style scoped></style>
