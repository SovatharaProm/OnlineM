<template>
  <div class="wrapper">
    <div class="profile-title flex">
      <div class="profile-title-detail w-[50%]">
        <div>
          <p class="text-2xl tracking-wide">Instructor</p>
          <p class="font-extrabold text-[40px] my-[1rem]">Mr. Sovathara Prom</p>
          <div class="flex items-center">
            <p class="font-semibold text-[24px]">Web Developer and UX/UI Instructor</p>
            <RouterLink to="/instructor/editaccount" class="edit-button">
              <Icon name="iconamoon:edit" class="edit-link" />
            </RouterLink>
          </div>
        </div>
        <div class="flex mt-[2rem]">
          <div>
            <p class="font-light text-[20px]">Total Student</p>
            <p class="font-bold text-[32px]">8,999</p>
          </div>
          <div class="ml-[5%]">
            <p class="font-light text-[20px]">Total Student</p>
            <p class="font-bold text-[32px]">8,999</p>
          </div>
        </div>
        <div class="mt-[3rem]">
          <p class="font-medium text-[24px] my-[1rem]">About Me</p>
          <p class="text-[#4E5566]">{{ Aboutme }}</p>
        </div>
        <div class="mt-[3rem]">
          <p class="font-medium text-[24px] my-[1rem]">Qualification</p>
          <p class="text-[#4E5566]">{{ quality }}</p>
        </div>
      </div>

      <div class="profile-title-image w-[50%] flex flex-col items-center">
        <div class="profile-image">
          <img :src="profileImage" class="h-[100%] w-[100%] object-cover" alt="image" />
        </div>
        <div class="mt-[1rem]">
          <div class="mb-[1rem]">
            <button class="btn">
              <Icon
                name="material-symbols:attachment"
                class="font-bold text-2xl icon mr-[0.3rem]" />
              <p>Website</p>
            </button>
          </div>
          <div class="mb-[1rem]">
            <button class="btn">
              <Icon name="devicon:linkedin" class="font-bold text-2xl icon mr-[0.3rem]" />
              <P>Linkedin</P>
            </button>
          </div>
          <div class="mb-[1rem]">
            <button class="btn">
              <Icon name="simple-icons:x" class="font-bold text-lg icon mr-[0.3rem]" />
              <p>Twitter</p>
            </button>
          </div>
        </div>
      </div>
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
      FullName: 'Sovathara Prom',
      Aboutme:
        'Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here ', // shortened for brevity
      quality:
        'Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here Text will be display here ', // shortened for brevity
      website: 'https://example.com',
      linkedin: 'https://linkedin.com/in/example',
      Twitter: 'https://twitter.com/example',
      profileImage:
        'https://plus.unsplash.com/premium_photo-1670282393309-70fd7f8eb1ef?q=80&w=3387&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    };
  },
  methods: {
    visitWebsite() {
      window.open(this.website, '_blank');
    },
    visitLinkedin() {
      window.open(this.linkedin, '_blank');
    },
    visitTwitter() {
      window.open(this.Twitter, '_blank');
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
.profile-image {
  border-radius: 50%;
  overflow: hidden;
  height: 300px;
  width: 300px;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
}
.btn {
  color: black;
  padding: 0.5rem 2rem;
  border-radius: 6px;
  border: 1px solid grey;
  font-size: 0.8rem;
  font-weight: bold;
  cursor: pointer;
  width: 150px;
  display: flex;
  align-items: center;
  p {
    font-weight: 400;
  }
}
.edit-button {
}

.edit-link {
  border-radius: 50%;
  font-size: 2.5rem;
  margin-left: 1.5rem;
  background-color: #2b348f;
  color: white;
  cursor: pointer;
  height: auto;
  padding: 0.5rem;
}
</style>
