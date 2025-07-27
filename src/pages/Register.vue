<template>
  <div class="mx-auto max-w-screen-xl px-4 py-8 sm:px-6 sm:py-12 lg:px-8 lg:py-16 flex items-center justify-center">
    <div class="bg-white rounded-2xl shadow-lg p-8 w-full max-w-md">
      <h2 class="text-3xl font-bold text-indigo-700 text-center mb-4">Sign Up</h2>

      <form @submit.prevent="handleSignup" class="space-y-4">
        <div>
          <label class="block text-sm font-medium text-gray-700">Name</label>
          <input v-model="name" type="text" required
            class="w-full mt-1 px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-300 focus:outline-none" />
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700">Username</label>
          <input v-model="username" type="text" required
            class="w-full mt-1 px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-300 focus:outline-none" />
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700">Email</label>
          <input v-model="email" type="email" required
            class="w-full mt-1 px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-pink-300 focus:outline-none" />
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700">Age</label>
          <input v-model="age" type="number" min="1" required
            class="w-full mt-1 px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-300 focus:outline-none" />
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700">Role</label>
          <input v-model="role" type="text" required
            class="w-full mt-1 px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-300 focus:outline-none" />
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700">Password</label>
          <input v-model="password" type="password" required
            class="w-full mt-1 px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-pink-300 focus:outline-none" />
        </div>

        <button type="submit"
          class="w-full bg-gradient-to-r from-pink-500 to-indigo-500 text-white py-2 rounded-lg font-semibold hover:from-pink-600 hover:to-indigo-600 transition">
          Sign Up
        </button>
      </form>

      <!-- Show response after submit -->
      <div v-if="submittedData" class="mt-6 p-4 bg-green-50 border border-green-200 rounded-lg text-sm text-gray-800">
        <h3 class="font-semibold text-green-700 mb-2">Server Response:</h3>
        <pre class="whitespace-pre-wrap break-words">{{ submittedData }}</pre>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      name: '',
      username: '',
      email: '',
      age: '',
      role: '',
      password: '',
      submittedData: null
    };
  },
  methods: {
    async handleSignup() {
      try {
        const res = await axios.post('https://jsonplaceholder.typicode.com/posts', {
          name: this.name,
          username: this.username,
          email: this.email,
          age: this.age,
          role: this.role,
          password: this.password
        });

        this.submittedData = res.data;

        // Optional: reset form if you want
        this.name = '';
        this.username = '';
        this.email = '';
        this.age = '';
        this.role = '';
        this.password = '';
      } catch (err) {
        const msg = err.response?.data?.message || 'Registration failed';
        alert(msg);
      }
    }
  }
};
</script>
