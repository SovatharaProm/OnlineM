<template>
    <div>
          <div class="header">
              <div class="flex justify-between items-center mb-4">
                  <p class="font-bold text-4xl p">Create Lesson</p>
              </div>
          </div>
       
      <div id="app">
              <div class="title" style="margin-bottom: 20px;">
                <p class="font-bold text-2m p">Lesson Title</p>
                <input v-model="newCourseTitle" type="text" placeholder="Input Title" class="border-2 border-gray-300 p-2 rounded-md">
              </div>
  
            <div class="description" ref="description">
              <p class="font-bold text-2m p">Lesson Description</p>
              <input v-model="newCourseDescription" ref="inputDescription" type="text" placeholder="Input Description" class="border-2 border-gray-300 p-2 rounded-md" @input="adjustWidth">
            </div>
          </div>
  
          <div class="upload">
            <p class="font-bold text-2m p">Upload Lesson</p>
          </div>
          <div>
    <form @submit.prevent="submitFiles" enctype="multipart/form-data">
      <label for="myfile"></label>
      <input type="file" id="myfile" name="myfile" ref="fileInput" multiple><br><br>
    </form>
  </div>
  <div>
    <button type="submit" class="submit-button" @click="submitForm">Submit</button>
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
    .upload p
    {
      margin-top: 20px;
    }
  
  .box {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }
  
  .box select {
    margin-right: 10px; 
  }
  .selects {
    display: flex;
    flex-direction: column;
  }
  
  .submit-button {
    margin-top: 20px;
    padding: 8px 16px;
    background-color: #2B348F;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
  }
  
  .submit-button:hover {
    background-color: #2B348F;
  }
    </style>
      