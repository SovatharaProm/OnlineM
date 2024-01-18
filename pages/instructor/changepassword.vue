<template>
  <div class="change-password">
    <h2 class="font-bold text-2xl p-[20px]">Change Password</h2>
    <form @submit.prevent="changePassword">
      <div class="form-group">
        <label for="currentPassword">Current Password:</label>
        <input
          type="password"
          id="currentPassword"
          v-model="currentPassword"
          required
        />
      </div>
      <div class="form-group">
        <label for="newPassword">New Password:</label>
        <input
          type="password"
          id="newPassword"
          v-model="newPassword"
          required
        />
      </div>
      <div class="form-group">
        <label for="confirmPassword">Confirm New Password:</label>
        <input
          type="password"
          id="confirmPassword"
          v-model="confirmPassword"
          required
        />
      </div>
      <button type="submit">Change Password</button>
    </form>
  </div>
</template>

<script>
import Dashboard from "~/layouts/dashboard.vue";

definePageMeta({
  layout: "dashboard",
});
export default {
  components: {
    Dashboard,
  },
  data() {
    return {
      currentPassword: '',
      newPassword: '',
      confirmPassword: '',
    };
  },
  methods: {
    changePassword() {
     
      if (this.validateForm()) {
      
        console.log('Changing password...');
        console.log('Current Password:', this.currentPassword);
        console.log('New Password:', this.newPassword);
        console.log('Confirm Password:', this.confirmPassword);

       
        this.currentPassword = '';
        this.newPassword = '';
        this.confirmPassword = '';
      }
    },
    validateForm() {
      
      if (!this.currentPassword || !this.newPassword || !this.confirmPassword) {
        alert('Please fill in all fields.');
        return false;
      }

      if (this.newPassword !== this.confirmPassword) {
        alert('New password and confirm password must match.');
        return false;
      }

     

      return true;
    },
  },
};
</script>

<style scoped>
.change-password {
  max-width: 400px;
  margin: 0 auto;
}

.form-group {
  margin-bottom: 1rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
}

input {
  width: 100%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 6px;
  margin-top: 0.5rem;
}

button {
  padding: 8px 16px;
  background-color: #2b348f;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 14px;
}

button:hover {
  background-color: #2b348f;
}
</style>
