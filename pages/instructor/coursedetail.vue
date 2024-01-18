<template>
  <div>
    <div class="flex justify-between items-center mb-4">
      <p class="font-bold text-4xl">Courses</p>
      <router-link to="/instructor/createlesson" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Create Lesson
      </router-link>
    </div>

    <div class="stats-wrapper">
      <Lesson
        v-for="(course, index) in courses"
        :key="index"
        :courseTitle="course.title"
        :spacing="spacing"
        @edit="editCourse(index)"
        @delete="deleteCourse(index)"
      />
      <router-link v-for="course in courseList" :to="'/instructor/editlesson'" class="text-black no-underline">
        <CreateCourse :courseTitle="course.title" :spacing="spacing" />
      </router-link>
    </div>
    <div>
    <div v-for="(lesson, index) in lessons" :key="index">
      <p>{{ lesson.title }}</p>
 
      <button @click="editLesson(lesson.id)">Edit</button>
    </div>
  </div>
</div>
  </template>
  
  <script setup>
  definePageMeta({
  layout: 'dashboard',
});
  import { ref } from 'vue';
  import Lesson from '@/components/Lesson.vue'; 

  // Data for courses
  const courses = ref([
  { id: 1, title: 'Lesson 1' },
  { id: 2, title: 'Lesson 2' },
  { id: 3, title: 'Lesson 3' },
  { id: 4, title: 'Lesson 4' },
  { id: 5, title: 'Lesson 5' },
  { id: 6, title: 'Lesson 6' },
 
  ]);
  
  const spacing = '1rem'; 
  
 
  const createCourse = () => {
   
  };
  const editCourse = (index) => {
  
  console.log(`Edit lesson ${index + 1} clicked`);
};

const deleteCourse = (index) => {
  
  console.log(`Delete lesson ${index + 1} clicked`);
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
  </style>
  