<template>
  <div class="profile">
    <div class="profile-header">
      <!-- Profile picture -->
      <img src="assets/images/Yuumi.png" alt="Profile Picture" class="profile-pic">
    </div>
    <div class="profile-info">
      <h2>Profile Information</h2>
      <form @submit.prevent="updateProfile">
        <div class="form-group">
          <label for="aboutMe">About me</label>
          <textarea placeholder="About me..." v-model="Aboutme"></textarea>
        </div>
        <div class="form-group">
          <label for="biography">Biography</label>
          <textarea placeholder="Biography..." v-model="bio"></textarea>
        </div>
        <div class="form-group">
          <label for="website">Website</label>
          <input type="text" id="website" v-model="website">
        </div>
        <div class="form-group">
          <label for="linkedin">Linkedin</label>
          <input type="text" id="linkedin" v-model="linkedin">
        </div>
        <div class="form-group">
          <label for="twitter">Twitter</label>
          <input type="text" id="twitter" v-model="Twitter">
        </div>
        <div class="button">
          <router-link :to="`/instructor/editaccount`" class="button">
            Edit Account Information
          </router-link>
        </div>
      </form>
    </div>
  </div>
</template>
  
  <script>
import Dashboard from '~/layouts/dashboard.vue';
definePageMeta({
  layout: 'dashboard',
});

export default {
    components: {
        Dashboard,
    },
    data() {
    return {
      Aboutme: '',
      bio: '',
      website: '',
      linkedin: '',
      Twitter: ''
    };
  },
  methods: {
    updateProfile() {
      // Handle updating profile logic here
      console.log('Profile updated:', {
        Aboutme: this.Aboutme,
        bio: this.bio,
        website: this.website,
        linkedin: this.linkedin,
        Twitter: this.Twitter
      });
    },
  },
};

  </script>
  
  <style>
  /* Style your profile page as needed */
  .profile {
  display: flex;
  flex-direction: column;
  align-items: center; /* Align items in the center horizontally */
  padding: 30px;
}

.profile-header {
  padding: 10px;
}

.profile-pic {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  margin-right: 10rem;
}

.profile-info {
  margin-top: 20px; /* Adjust the margin between picture and form */
}
.profile-info h2 {
  margin-top: 20px;
  font-weight: bold;
}

.form-group {

    margin-bottom: 20px;
}
  
  input[type="text"],
  input[type="date"],
  input[type="password"] {
    width: 100%;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  .textarea-container {
  position: relative;
}
.form-group textarea {
  width: 100%;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
  resize: vertical;
  overflow-y: hidden; /* Hide vertical scrollbar */
  min-height: 120px; /* Set a minimum height */
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1); /* Add a box-shadow for a visible textarea */
}

/* Adjust label position */
.form-group > label {
  display: block;
  margin-bottom: 6px;
}
.button {
    padding: 10px 10px;
    background-color: #2B348F;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    width: 15rem;
  }
  </style>
  