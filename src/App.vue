


<template>


<main class="app">

<section class="greeting">
  <h1 class="title">
    &#9743; Welcome back,<input type="text" placeholder="Enter Name" v-model="EnterN">
  </h1>
</section>


  <div>
    <h2>Create A New Contact List</h2>

    <p>Create the new contact by filling in the information below..</p>
    <form @submit.prevent="addContact">
      <input type="text" v-model="name" placeholder="Name" required>
      <input type="text" v-model="phonenumber" placeholder="Phone Number" required>
      <input type="text" v-model="email" placeholder="Email" required>

      <button type="submit">Add Contact</button>
      
    </form>
    <ul>
      <h3> Contact List</h3>
      <li v-for="contact in contacts" :key="contact.id">{{ contact.name }} - {{ contact.phonenumber }} - {{ contact.email }}</li>
    </ul>
  </div>


  </main>

</template>



<script>
export default {
  data() {
    return {
      name: '',
      phonenumber: '',
      email: '',
      contacts: []
    };
  },
  methods: {
    addContact() {
      this.contacts.push({ id: Date.now(), name: this.name, phonenumber: this.phonenumber, email: this.email });
      this.name = '';
      this.phonenumber = '';
      this.email ='';
    }
  }
};

</script>

