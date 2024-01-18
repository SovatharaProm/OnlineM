<template>
  <div>
    <div class="flex justify-between items-center mb-4">
      <p class="font-bold text-4xl">All Courses</p>
      <router-link to="/instructor/createcourse" class="bg-blue-900 hover:bg-blue-800 text-white font-bold py-2 px-4 rounded">
        Create Courses
      </router-link>
    </div>

    <div class="stats-wrapper">
      <router-link v-for="course in courseList" :to="'/instructor/coursedetail'" class="text-black no-underline">
        <CreateCourse :courseTitle="course.title" :spacing="spacing" />
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
        courseList: [
          { id: 1, title: 'Cloud Computing' },
          { id: 2, title: 'Web Development' },
          { id: 3, title: 'Another Course' },
          
        ],
        spacing: '1rem', 
      };
    },
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
