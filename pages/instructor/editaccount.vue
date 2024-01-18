<template>
  <div class="wrapper">
    <div class="profile-title flex">
      <div class="profile-title-detail w-[50%]">
        <div>
          <p class="text-2xl tracking-wide">Instructor</p>
          <form @submit.prevent="submitForm">
            <div class="form-group">
              <label for="fullName">Full Name:</label>
              <input
                type="text"
                id="fullName"
                v-model="editedFullName"
                class="form-input"
              />
            </div>
            <div class="form-group">
              <label for="aboutMe">About Me:</label>
              <textarea
                id="aboutMe"
                v-model="editedAboutMe"
                class="form-input"
              ></textarea>
            </div>
            <div class="form-group">
              <label for="qualification">Qualification:</label>
              <textarea
                id="qualification"
                v-model="editedQualification"
                class="form-input"
              ></textarea>
            </div>
            <div class="form-group">
              <label for="website">Website:</label>
              <input
                type="text"
                id="website"
                v-model="editedWebsite"
                class="form-input"
              />
            </div>
            <div class="form-group">
              <label for="twitter">Twitter:</label>
              <input
                type="text"
                id="twitter"
                v-model="editedTwitter"
                class="form-input"
              />
            </div>
            <div class="form-group">
              <label for="linkedin">LinkedIn:</label>
              <input
                type="text"
                id="linkedin"
                v-model="editedLinkedin"
                class="form-input"
              />
            </div>
            <div class="save-button">
              <router-link :to="`/instructor/viewprofile`">
              Save
            </router-link>
            </div>
            
          </form>
        </div>
      </div>

      <div class="profile-title-image w-[50%] flex flex-col items-center">
        <div class="profile-image">
          <img :src="profileImage" class="h-[100%] w-[100%] object-cover" />
        </div>
      </div>
    </div>
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
      editedFullName: "",
      editedAboutMe: "",
      editedQualification: "",
      editedWebsite: "",
      editedTwitter: "",
      editedLinkedin: "",
      profileImage:
        "https://plus.unsplash.com/premium_photo-1670282393309-70fd7f8eb1ef?q=80&w=3387&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
    };
  },
  methods: {
    submitForm() {
      // Here you can handle the form submission
      // Update the user's account details with the edited values
      console.log("Form submitted with edited data:", {
        editedFullName: this.editedFullName,
        editedAboutMe: this.editedAboutMe,
        editedQualification: this.editedQualification,
        editedWebsite: this.editedWebsite,
        editedTwitter: this.editedTwitter,
        editedLinkedin: this.editedLinkedin,
      });
    },
  },
};
</script>

<style>
.wrapper {
  padding: 2rem;
  background: white;
  border-radius: 14px;
  margin-bottom: 2rem;
}

.form-group {
  margin-bottom: 1rem;
}

.form-input {
  width: 100%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 6px;
  margin-top: 0.5rem;
}

.edit-link {
  background-color: #2b348f;
  color: white;
  cursor: pointer;
}
.save-button {
  padding: 8px 16px;
  background-color: #2b348f;
  color: white;
  border: none;
  cursor: pointer;
  width: fit-content;
}
</style>
