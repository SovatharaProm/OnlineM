<template>
  <div>
        <div class="header">
            <div class="flex justify-between items-center mb-4">
                <p class="font-bold text-4xl p">Create your Course</p>
            </div>
        </div>
     
    <div id="app">
            <div class="title" style="margin-bottom: 20px;">
              <p class="font-bold text-2m p">Course Title</p>
              <input v-model="newCourseTitle" type="text" placeholder="Input Title" class="border-2 border-gray-300 p-2 rounded-md">
            </div>

          <div class="description" ref="description">
            <p class="font-bold text-2m p">Course Description</p>
            <input v-model="newCourseDescription" ref="inputDescription" type="text" placeholder="Input Description" class="border-2 border-gray-300 p-2 rounded-md" @input="adjustWidth">
          </div>
        </div>

        <div class="basic">
          <p class="font-bold text-2m p">Basic Info</p>
        </div>
        <div class="box">
    <form @submit.prevent="submitForm">
      <select v-model="selectLanguage">
        <option value="" disabled>Select Language</option>
        <option value="English">English - EN</option>
        <option value="Khmer">Khmer - KH</option>
        <option value="Spain">Spain - ES</option>
      </select>

      <select v-model="selectLevel">
        <option value="" disabled>--Select Level--</option>
        <option value="Easy">Easy</option>
        <option value="Intermediate">Intermediate</option>
        <option value="Expert">Expert</option>
      </select>

      <select v-model="selectCategory">
        <option value="" disabled>--Select Category--</option>
        <option value="CS">CS - Computer Science</option>
        <option value="BUS">BUS - Business</option>
        <option value="Social">Social - Social Studies</option>
      </select>
    </form>
  </div>
  <div class="submit-button" style="padding: 4px 8px; font-size: 14px;">
    <router-link to="/instructor/course">
      Submit
    </router-link>
  </div>
</div>
  </template>
  
  
  <script>
    definePageMeta({
    layout: 'dashboard',
  });
  import CreateCourse from '@/components/CreateCourse.vue'; 
  
  export default {
    components: {
      CreateCourse,
    },
    data() {
    return {
      selectLanguage: '',
      selectLevel: '',
      selectCategory: ''
    };
  },
  methods: {
    submitForm() {
     
      console.log('Submitted!', this.selectLanguage, this.selectLevel, this.selectCategory);
    }
  }
};
  </script>
  
  <style>
  
  .stats-wrapper {
    display: flex;
    flex-direction: column;
    padding: 2rem;
    background: white;
    border-radius: 14px;
    margin-top: 2rem;
  }
  .header p {
    margin: 0 auto; 
  }
  .title
  {
    display: flex;
    flex-direction: column;
    margin-bottom: 40px;
  }
    .title input {
        width: 25rem;
        height: 50px; 
        border: 2px solid #ccc;
        padding: 10px;
        border-radius: 5px;
        resize: vertical; 
    }
  .description {
    display: flex;
    flex-direction: column;
    margin-top: 20px;
  }


  .description input {
    width: 60rem;
    height: 100px;
    border: 2px solid #ccc;
    padding: 10px;
    border-radius: 5px;
    resize: vertical; 
  }
  .basic p
  {
    margin-top: 20px;
  }

.box {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.box select {
  margin-right: 20px; 
}
.selects {
  display: flex;
  flex-direction: column;
}

.submit-button {
  margin-top: 50px;
  padding: 10px 20px;
  background-color: #2B348F;
  color: white;
  border: none;
  border-radius: 2px;
  cursor: pointer;
  font-size: 20px;
  width: 5rem;
}

.submit-button:hover {
  background-color: #2B348F;
}
  </style>
    