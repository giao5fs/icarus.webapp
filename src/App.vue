<script>
import axios from 'axios'
export default {
  data() {
    return {
      form: {
        email: '',
        firstname: '',
        lastname: ''
      }
    };
  },
  methods: {
    async submitForm() {
      try {
        const response = await axios.post('https://localhost:7114/api/member/register', this.form);
        console.log(response);
      } catch (error) {
        console.error(error);
      }
    }
  }
}
</script>

<template>
  <main>
    <div class="container">
      <form @submit.prevent="submitForm">
        <h1>Register member</h1>
        <div class="form-group">
          <label for="email">Email:</label>
          <input type="email" class="form-control" id="email" v-model="form.email">
        </div>
        <div class="form-group">
          <label for="firstname">First name:</label>
          <input type="text" class="form-control" id="firstname" v-model="form.firstname">
        </div>
        <div class="form-group">
          <label for="lastname">Last name:</label>
          <input type="text" class="form-control" id="lastname" v-model="form.lastname">
        </div>
        <!-- <div class="form-group">
          <label for="password">Password:</label>
          <input type="password" class="form-control" id="password" v-model="form.password">
        </div> -->
        <button type="submit" class="btn btn-primary">Submit</button>
      </form>
    </div>
  </main>
</template>

<style scoped>
main {
  font-family: sans-serif;
  width: 100vw;
  height: 100vh;
}

.container {
  width: 1000px;
  height: 50%;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
}

form h1 {
  text-align: center;
}

.form-group {
  display: flex;
  flex-direction: column;
  margin-bottom: 1rem;
  width: 500px;
}

label {
  font-weight: bold;
  margin-bottom: 0.5rem;
}

input[type="text"],
input[type="email"],
input[type="password"] {
  padding: 0.5rem;
  border-radius: 0.25rem;
  border: 1px solid #ccc;
}

.btn {
  padding: 0.75rem 1.5rem;
  background-color: #42b983;
  color: #fff;
  border-radius: 0.25rem;
  border: none;
  cursor: pointer;
}
</style>