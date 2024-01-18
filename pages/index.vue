<template>
  <div class="py-[2%]">
  
    <div class="intro-card">
      <div><p class="font-bold text-4xl mb-4">Welcome back, User!</p></div>
      <div><p>Keep it up and improve your progress.</p></div>
    </div>

    <div class="stats-wrapper">
      <div class="stats-box">
        <div class="px-[2%]">
          <p class="font-bold text-4xl">Total</p>
          <p class="text-slate-500">This month</p>
        </div>
        <div class="px-[2%]">
          <p class="text-xl font-bold">Revenue</p>
          <p class="text-3xl">$8,500</p>
          <p class="text-slate-500">$0.00</p>
        </div>
        <div class="px-[2%]">
          <p class="text-xl font-bold">Enrollment</p>
          <p class="text-3xl">6,800</p>
          <p class="text-slate-500">450</p>
        </div>
      </div>

      <div v-for="(course, index) in courses" :key="index" class="course-wrapper">
        <div class="highlight"></div>
        <div><p>{{ course.name }}</p></div>
        <div></div>
      </div>
    </div>
  </div>
</template>

<script setup>
definePageMeta({
  layout: 'dashboard',
});

const courses = ref([
  { id: 1, name: 'Cloud Computing' },
  { id: 2, name: 'Web Development' },
  { id: 3, name: 'Web Development' },
  { id: 4, name: 'Web Development' },
  { id: 5, name: 'Web Development' },

]);
</script>

<style scoped>
.intro-card {
  background: #2b348f;
  padding: 2rem;
  color: white;
  border-radius: 14px;
}
.stats-wrapper {
  display: flex;
  flex-direction: column;
  padding: 2rem;
  background: white;
  border-radius: 14px;
  margin-top: 2rem;
}
.stats-box {
  display: flex;
  margin-bottom: 1rem;
}
.course-wrapper {
  position: relative;
  width: 100%;
  padding: 1.5rem; 
  margin-bottom: 1rem;
  box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
  border-radius: 6px;
  overflow: hidden;
}
.highlight {
  position: absolute;
  top: 0;
  left: 0;
  width: 0.7rem;
  height: 100%;
  background: #2b348f;
}
</style>
